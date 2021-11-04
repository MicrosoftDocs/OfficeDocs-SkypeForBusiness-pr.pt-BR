---
title: Solicitação de Certificado (Básico)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: A página Nome e Segurança Configurações fornece uma caixa de texto para definir um Nome Amigável, uma listada para o comprimento de bit do par de chaves pública e privada e uma caixa de seleção que permite marcar a chave privada do certificado como exportável.
ms.openlocfilehash: 445a71c4655a8325de85165f1970b85fc536dff9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764269"
---
# <a name="certificate-request-basic"></a>Solicitação de Certificado (Básico)
 
A página Nome e Segurança **Configurações** fornece uma caixa de texto para definir  um Nome Amigável **,** uma listada para o comprimento de bit do par de chaves pública e privada e uma caixa de seleção que permite marcar a chave privada do certificado como **exportável**.
  
O nome amigável, ou simples, em um certificado é um nome facilmente reconhecível que facilita a identificação para a pessoa que exibe o certificado.
  
O Comprimento de bit da par de chave pública e privada pode ser selecionado como 1024, 2048 ou 4096.
  
Selecionar a caixa de seleção para Marcar a chave privada do certificado como **exportável** permite que o certificado e a chave privada sejam exportados e movidos para outro computador ou servidor. A única vez que isso é necessário é quando você está criando um pool de Servidores de Borda para o serviço de autenticação de retransmissão de mídia (MRAS).
  
> [!CAUTION]
> Para ajudar a manter a segurança do certificado e do par de chaves, você deve selecionar a opção Marcar a chave privada do certificado como exportável somente se for absolutamente necessário. 
  

