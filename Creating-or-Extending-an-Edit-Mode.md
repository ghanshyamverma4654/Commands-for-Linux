using System;
using System.Web;
using System.ComponentModel;
using System.Net;


namespace FiqueRico.BL
{
    public class Caixa
    {
        System.Net.WebClient wc;

        private int _tentativas = 0;
        public Caixa()
        {
            wc = new System.Net.WebClient();
        }

        /// <summary>
        /// Obtem o sorteio da caixa
        /// Contém alguns parametros necessários para que a Caixa libere o resultado.
        /// </summary>
        /// <param name="tipo">Megasena por exemplo</param>
        /// <param name="numConcurso">numero do concurso desejado</param>
        /// <returns></returns>
        public string ObterSorteioNaCaixa(TipoJogo tipo, int numConcurso)
        {
            string url = String.Empty;

            switch (tipo)
            {
                //case TipoJogo.Megasena:
                //    url = (@"http://www1.caixa.gov.br/loterias/loterias/megasena/megasena_pesquisa_new.asp?submeteu=sim&opcao=concurso&txtConcurso=" + numConcurso);
                //    //wc.Headers.Add("Accept-Encoding", "gzip, deflate");
                //    wc.Headers.Add("Accept-Language", "en-us");
                //    wc.Headers.Add("Cookie", "security=true; ASPSESSIONIDCASBDBSR=KAFBHFNBANPMMKKJNAICCGKF");
                //    wc.Headers.Add("Referer", "http://www1.caixa.gov.br/loterias/loterias/megasena/megasena_resultado.asp");
                //    //web.Headers.Add("Connection", "Keep-Alive");
                //    //web.Headers.Add("Host", "www1.caixa.gov.br");
                //    break;
                //case TipoJogo.Quina:
                    //url = (@"http://www1.caixa.gov.br/loterias/loterias/quina/quina_pesquisa_new.asp?submeteu=sim&opcao=concurso&txtConcurso=" + numConcurso);
                    // wc.Headers.Add("Accept-Language", "en-us");
                    // wc.Headers.Add("Cookie", "security=true; ASPSESSIONIDSSRSRQCA=CAJLHKOAMCHHFNDAPLLPIMIA");
                    //wc.Headers.Add("Referer", "http://www1.caixa.gov.br/loterias/loterias/quina/quina_resultado.asp");
                    //break;
                case TipoJogo.DuplaSena:
                    url = (@"http://www1.caixa.gov.br/loterias/loterias/duplasena/duplasena_pesquisa_new.asp?submeteu=sim&opcao=concurso&txtConcurso=" + numConcurso);
                    break;
                case TipoJogo.Lotogol:
                    url = (@"http://www1.caixa.gov.br/loterias/loterias/lotogol/lotogol_pesquisa_new.asp?submeteu=sim&opcao=concurso&txtConcurso=" + numConcurso);
                    break;
                case TipoJogo.TimeMania:
                    url = (@"http://www1.caixa.gov.br/loterias/loterias/timemania/timemania_pesquisa.asp?submeteu=sim&opcao=concurso&txtConcurso=" + numConcurso);
                    break;
                case TipoJogo.LotoMania:
                    url = (@"http://www1.caixa.gov.br/loterias/loterias/lotomania/_lotomania_pesquisa.asp?submeteu=sim&opcao=concurso&txtConcurso=" + numConcurso);
                    break;
                case TipoJogo.LotoFacil:
                    url = (@"http://www1.caixa.gov.br/loterias/loterias/lotofacil/lotofacil_pesquisa_new.asp?submeteu=sim&opcao=concurso&txtConcurso=" + numConcurso);
                    break;
                default:
                    return null;
            }

            if (_tentativas == 3)
                throw new FiqueRico.BL.Exception.CaixaRequestFailureException();
            try
            {
                wc.Headers.Add("User-Agent", "Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; .NET4.0C; .NET4.0E; .NET CLR 2.0.50727; .NET CLR 3.0.4506.2152; .NET CLR 3.5.30729; InfoPath.2; OfficeLiveConnector.1.3; OfficeLivePatch.0.0)");
                wc.Headers.Add("Accept", "*/*");
                //vai retornar o JSON com os dados do sorteio e não a URL
                url = wc.DownloadString(url);
            }
            catch (System.Net.WebException)
            {
                Console.WriteLine("O servidor não respondeu corretamente a requisição");
                _tentativas++;
                ObterSorteioNaCaixa(tipo, numConcurso);
            }
            catch (System.Exception ex)
            {
                Console.WriteLine(ex.Message);
                _tentativas++;
                ObterSorteioNaCaixa(tipo, numConcurso);
            }

            return url;
        }
    }
}