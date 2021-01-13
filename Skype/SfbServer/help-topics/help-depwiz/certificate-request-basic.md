---
title: Solicitação de Certificado (Básico)
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: A página Nome e Configurações de Segurança fornece uma caixa de texto para definir um Nome Amigável, uma lista drop-down para o comprimento de bit do par de chaves pública e privada e uma caixa de seleção que permite marcar a chave privada do certificado como exportável.
ms.openlocfilehash: f0d0339a483056276d400654f897b898b002cf03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805341"
---
# <a name="certificate-request-basic"></a>Solicitação de Certificado (Básico)
 
A  página Nome e Configurações de Segurança fornece uma caixa de texto  para definir um Nome Amigável **,** uma lista drop-down para o comprimento de bit do par de chaves pública e privada e uma caixa de seleção que permite marcar a chave privada do certificado como **exportável.**
  
O nome amigável, ou simples, em um certificado é um nome facilmente reconhecível que facilita a identificação para a pessoa que exibe o certificado.
  
O Comprimento de bit da par de chave pública e privada pode ser selecionado como 1024, 2048 ou 4096.
  
Marcar a caixa de seleção Marcar a chave privada do certificado como **exportável** permite que o certificado e a chave privada sejam exportados e movidos para outro computador ou servidor. A única vez que isso é necessário é quando você está criando um pool de Servidores de Borda para o serviço de autenticação de retransmissão de mídia (MRAS).
  
> [!CAUTION]
> Para ajudar a manter a segurança do certificado e do par de chaves, você deve selecionar a opção Marcar a chave privada do certificado como exportável somente se for absolutamente necessário. 
  

