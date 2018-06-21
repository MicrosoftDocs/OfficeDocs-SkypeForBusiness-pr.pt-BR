---
title: Solicitação de Certificado (Básico)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: A página nome e configurações de segurança fornece uma caixa de texto para definir um nome amigável, uma lista suspensa para o comprimento de Bit de uma caixa de seleção que permite que você marcar a chave privada do certificado como exportável e o par de chaves público e privado.
ms.openlocfilehash: 9b8e306c9fa7611622e293185dcf08ff97d3e876
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19991982"
---
# <a name="certificate-request-basic"></a>Solicitação de Certificado (Básico)
 
A página **nome e configurações de segurança** fornece uma caixa de texto para definir um **Nome amigável**, uma lista suspensa para o **comprimento de Bit** do par de chaves público e privado e uma caixa de seleção que permite a você **marca o certificado a chave privada como exportável**.
  
O nome amigável, ou simples, em um certificado é um nome facilmente reconhecível que facilita a identificação para a pessoa que exibe o certificado.
  
O Comprimento de bit da par de chave pública e privada pode ser selecionado como 1024, 2048 ou 4096.
  
Marcar a caixa de seleção para **marcar a chave privada do certificado como exportável** permite que o certificado e a chave particular sejam exportadas e movido para outro computador ou servidor. A única vez que isso é necessário é quando você está criando um pool de Servidores de Borda para o serviço de autenticação de retransmissão de mídia (MRAS).
  
> [!CAUTION]
> Para ajudar a manter a segurança do certificado e o par de chaves, você deve selecionar a marca de chave privada do certificado como exportável opção somente se for absolutamente necessário. 
  

