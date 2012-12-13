-- phpMyAdmin SQL Dump
-- version 3.2.3
-- http://www.phpmyadmin.net
--
-- Host: localhost
-- Generation Time: Dec 14, 2012 at 12:56 AM
-- Server version: 5.1.40
-- PHP Version: 5.3.13

SET SQL_MODE="NO_AUTO_VALUE_ON_ZERO";

--
-- Database: `nat`
--

-- --------------------------------------------------------

--
-- Table structure for table `fizicheskie_lica`
--

CREATE TABLE IF NOT EXISTS `fizicheskie_lica` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `title` text NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=cp1251 AUTO_INCREMENT=3 ;

--
-- Dumping data for table `fizicheskie_lica`
--

INSERT INTO `fizicheskie_lica` (`id`, `title`) VALUES
(1, 'genkaKO'),
(2, 'ygorstroi');

-- --------------------------------------------------------

--
-- Table structure for table `kontragenti`
--

CREATE TABLE IF NOT EXISTS `kontragenti` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `title` text NOT NULL,
  `id_fiz_lico` int(11) NOT NULL,
  `id_ur_lico` int(11) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=cp1251 AUTO_INCREMENT=31 ;

--
-- Dumping data for table `kontragenti`
--

INSERT INTO `kontragenti` (`id`, `title`, `id_fiz_lico`, `id_ur_lico`) VALUES
(23, 'rogaikopita', 0, 1),
(24, 'genkaKO', 1, 0),
(25, 'ygorstroi', 2, 0),
(27, 'cocapollo', 0, 2),
(29, 'Я', 0, 0);

-- --------------------------------------------------------

--
-- Table structure for table `operaciya`
--

CREATE TABLE IF NOT EXISTS `operaciya` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `tip` int(1) NOT NULL,
  `data` date NOT NULL,
  `nomer` int(11) NOT NULL,
  `ot_kogo` int(11) NOT NULL,
  `komy` int(11) NOT NULL,
  `user_id` int(11) NOT NULL,
  `summa` double NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=cp1251 AUTO_INCREMENT=2 ;

--
-- Dumping data for table `operaciya`
--

INSERT INTO `operaciya` (`id`, `tip`, `data`, `nomer`, `ot_kogo`, `komy`, `user_id`, `summa`) VALUES
(1, 0, '2012-11-06', 1, 29, 23, 1, 10000);

-- --------------------------------------------------------

--
-- Table structure for table `Prais`
--

CREATE TABLE IF NOT EXISTS `Prais` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user id` int(20) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM DEFAULT CHARSET=cp1251 AUTO_INCREMENT=1 ;

--
-- Dumping data for table `Prais`
--


-- --------------------------------------------------------

--
-- Table structure for table `svodnie_ostatki`
--

CREATE TABLE IF NOT EXISTS `svodnie_ostatki` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user` int(11) NOT NULL,
  `id_kontragenta` int(11) NOT NULL,
  `summa` double NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=cp1251 AUTO_INCREMENT=667 ;

--
-- Dumping data for table `svodnie_ostatki`
--


-- --------------------------------------------------------

--
-- Table structure for table `uridicheskie_lica`
--

CREATE TABLE IF NOT EXISTS `uridicheskie_lica` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `title` text NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=cp1251 AUTO_INCREMENT=3 ;

--
-- Dumping data for table `uridicheskie_lica`
--

INSERT INTO `uridicheskie_lica` (`id`, `title`) VALUES
(1, 'rogaikopita'),
(2, 'cocapollo');

-- --------------------------------------------------------

--
-- Table structure for table `users`
--

CREATE TABLE IF NOT EXISTS `users` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `login` varchar(50) NOT NULL,
  `password` varchar(25) NOT NULL,
  `email` text NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM  DEFAULT CHARSET=cp1251 AUTO_INCREMENT=3 ;

--
-- Dumping data for table `users`
--

INSERT INTO `users` (`id`, `login`, `password`, `email`) VALUES
(1, 'genka ', '1', ''),
(2, 'igor', '1', '');
