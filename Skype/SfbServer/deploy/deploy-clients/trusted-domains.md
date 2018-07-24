---
title: Domínios confiáveis do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leia este tópico para aprender a configurar domínios confiáveis do Sistema de Salas do Skype e do Skype for Business.
ms.openlocfilehash: b55d1558bd45cc8f0726b054fed60b2a4c5e4794
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983760"
---
# <a name="skype-room-system-trusted-domains"></a>Domínios confiáveis do Sistema de Salas do Skype
 
Leia este tópico para aprender a configurar domínios confiáveis do Sistema de Salas do Skype e do Skype for Business.
  
## <a name="trusted-domains"></a>Domínios confiáveis

O Skype para cliente corporativos exibe uma caixa de diálogo que permite aos usuários aceitar o certificado a partir do Skype para Business Server, se o domínio SIP da conta de usuário entrando for diferente do nome apresentado no assunto ou nome alternativo da entidade do certificado. Se o certificado configurado para Skype para Business Server em sua organização não tiver o nome de domínio SIP da conta de sistema do Skype sala no assunto ou nome alternativo da entidade, você deve configurar os domínios apresentados no certificado sob os domínios confiáveis chave do registro na máquina do console do sistema do Skype sala. Guia de sistema de sala Skype fornecida pelo fabricante Skype sala do administrador do sistema explica como e onde adicionar domínios confiáveis no Skype para o cliente de negócios. 
  
Por exemplo, suponha que os certificados configurados no Skype para Business Server têm um nome de Alt do assunto/assunto de "CONTOSO. "LOCAL" e um dos domínios SIP atribuídos a um usuário para o endereço de entrada no sistema de sala do Skype é "confrm1@contoso.net". Porque contoso.net é não no certificado, na máquina do sistema do Skype sala, você precisará configurar "contoso" como um domínio confiável no registro, conforme explicado no guia de sistema de sala Skype fornecida pelo fabricante Skype sala do administrador do sistema. 
  

