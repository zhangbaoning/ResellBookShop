# ResellBookShop
以下为数据库的代码，在命令行中输入创建数据库
<hr/>
<code>
/*
SQLyog 企业版 - MySQL GUI v8.14 
MySQL - 5.7.16 : Database - resell_bookstore
*********************************************************************
*/


/*!40101 SET NAMES utf8 */;

/*!40101 SET SQL_MODE=''*/;

/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;
CREATE DATABASE /*!32312 IF NOT EXISTS*/`resell_bookstore` /*!40100 DEFAULT CHARACTER SET utf8 */;

USE `resell_bookstore`;

/*Table structure for table `book` */

DROP TABLE IF EXISTS `book`;

CREATE TABLE `book` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `bookName` varchar(20) DEFAULT NULL,
  `bookType` varchar(20) DEFAULT NULL,
  `publish` varchar(20) DEFAULT NULL,
  `price` double DEFAULT NULL,
  `sellId` int(11) DEFAULT NULL,
  `buyId` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `FK_sell` (`sellId`),
  KEY `FK_buy` (`buyId`),
  CONSTRAINT `FK_buy` FOREIGN KEY (`buyId`) REFERENCES `user` (`id`),
  CONSTRAINT `FK_sell` FOREIGN KEY (`sellId`) REFERENCES `user` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

/*Data for the table `book` */

/*Table structure for table `user` */

DROP TABLE IF EXISTS `user`;

CREATE TABLE `user` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `userName` varchar(20) DEFAULT NULL,
  `password` varchar(20) DEFAULT NULL,
  `tel` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

/*Data for the table `user` */

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;
</code>
