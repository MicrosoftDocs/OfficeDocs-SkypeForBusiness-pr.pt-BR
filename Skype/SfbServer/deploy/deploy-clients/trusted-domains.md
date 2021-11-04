---
title: Skype Domínios confiáveis do Sistema de Sala
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leia este tópico para saber como configurar domínios confiáveis para Skype Room System e Skype for Business.
ms.openlocfilehash: 68449fcb0c1bf4fb608f7d1172b45776fe109958
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738968"
---
# <a name="skype-room-system-trusted-domains"></a>Skype Domínios confiáveis do Sistema de Sala
 
Leia este tópico para saber como configurar domínios confiáveis para Skype Room System e Skype for Business.
  
## <a name="trusted-domains"></a>Domínios confiáveis

O cliente Skype for Business exibe uma caixa de diálogo que permite que os usuários aceitem o certificado do Skype for Business Server se o domínio SIP da conta de usuário entrar for diferente do nome apresentado no Subject ou Subject Alt Name no certificado. Se o certificado configurado para Skype for Business Server em sua organização não tiver o nome de domínio SIP da conta do sistema de sala Skype em Subject ou Subject Alt Name, você deverá configurar esses domínios apresentados no certificado sob a chave de registro Domínios Confiáveis na máquina de console do Sistema de Sala Skype. O Skype do sistema de sala fornecido Skype Guia do Administrador do Sistema de Sala explica como e onde adicionar domínios confiáveis no cliente Skype for Business sala. 
  
Por exemplo, suponha que os certificados configurados no Skype for Business Server tenham um Nome Alt de Assunto/Assunto de "CONTOSO. LOCAL" e um dos domínios SIP atribuídos a um usuário para o endereço de Skype de login do Sistema de Sala é "confrm1@contoso.net". Como o contoso.net não está no certificado, no computador do sistema de sala Skype, você precisará configurar "contoso.local" como um domínio confiável no Registro, conforme explicado no guia do administrador do sistema de sala Skype fornecido pelo fabricante do Skype Room System. 
  

