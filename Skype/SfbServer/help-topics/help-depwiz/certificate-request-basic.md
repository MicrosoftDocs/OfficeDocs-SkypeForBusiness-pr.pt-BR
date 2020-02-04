---
title: Solicitação de Certificado (Básico)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: A página Configurações de segurança e nome fornece uma caixa de texto para definir um nome amigável, uma lista suspensa para o comprimento de bit do par de chaves privada e pública e uma caixa de seleção que permite marcar a chave privada do certificado como exportável.
ms.openlocfilehash: e3ee374ad9a1fc29f67b7f756dcb2fd0384bcabc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687784"
---
# <a name="certificate-request-basic"></a>Solicitação de Certificado (Básico)
 
A página **configurações de segurança e nome** fornece uma caixa de texto para definir um **nome amigável**, uma lista suspensa para o **comprimento de bit** do par de chaves privada e pública e uma caixa de seleção que permite **marcar a chave privada do certificado como exportável**.
  
O nome amigável, ou simples, em um certificado é um nome facilmente reconhecível que facilita a identificação para a pessoa que exibe o certificado.
  
O Comprimento de bit da par de chave pública e privada pode ser selecionado como 1024, 2048 ou 4096.
  
Marcar a caixa de seleção para **marcar a chave privada do certificado como exportável** permite que o certificado e a chave privada sejam exportados e movidos para outro computador ou servidor. A única vez que isso é necessário é quando você está criando um pool de Servidores de Borda para o serviço de autenticação de retransmissão de mídia (MRAS).
  
> [!CAUTION]
> Para ajudar a manter a segurança do certificado e do par de chaves, você deve selecionar a opção marcar a chave privada do certificado como exportável somente se for absolutamente necessária. 
  

