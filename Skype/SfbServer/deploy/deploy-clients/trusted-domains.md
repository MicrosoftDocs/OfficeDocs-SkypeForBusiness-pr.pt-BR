---
title: Domínios confiáveis do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leia este tópico para saber como configurar domínios confiáveis para o Sistema de Sala do Skype e o Skype for Business.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834111"
---
# <a name="skype-room-system-trusted-domains"></a>Domínios confiáveis do Sistema de Sala do Skype
 
Leia este tópico para saber como configurar domínios confiáveis para o Sistema de Sala do Skype e o Skype for Business.
  
## <a name="trusted-domains"></a>Domínios confiáveis

O cliente Skype for Business exibe uma caixa de diálogo que permite que os usuários aceitem o certificado do Skype for Business Server se o domínio SIP da conta de usuário que está se inando for diferente do nome apresentado no Nome Alt da Assunto ou assunto no certificado. Se o certificado configurado para o Skype for Business Server em sua organização não tiver o nome de domínio SIP da conta do Sistema de Sala do Skype em Assunto ou Nome Alt da Entidade, você deverá configurar esses domínios apresentados no certificado sob a chave do Registro de Domínios Confiáveis na máquina de console do Sistema de Sala do Skype. O Guia do Administrador do Sistema de Sala do Skype fornecido pelo fabricante do Sistema de Sala do Skype explica como e onde adicionar domínios confiáveis no cliente Skype for Business. 
  
Por exemplo, suponha que os certificados configurados no Skype for Business Server tenham um Nome Alt assunto/assunto de "CONTOSO. LOCAL" e um dos domínios SIP atribuídos a um usuário para o endereço de login do Sistema de Sala do Skype é "confrm1@contoso.net". Como o contoso.net não está no certificado, na máquina do Sistema de Sala do Skype, você precisará configurar "contoso.local" como um domínio confiável no Registro, conforme explicado no Guia do Administrador do Sistema de Sala do Skype fornecido pelo fabricante do Sistema de Sala do Skype. 
  

