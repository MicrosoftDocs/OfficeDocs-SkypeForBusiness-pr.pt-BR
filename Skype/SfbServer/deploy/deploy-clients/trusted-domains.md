---
title: Skype domínios confiáveis do Sistema de Sala
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: f3ea0557c22214addd0f7cc4d935af919a131ae1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399925"
---
# <a name="skype-room-system-trusted-domains"></a>Skype domínios confiáveis do Sistema de Sala
 
Leia este tópico para saber como configurar domínios confiáveis para Skype Room System e Skype for Business.
  
## <a name="trusted-domains"></a>Domínios confiáveis

O cliente Skype for Business exibe uma caixa de diálogo que permite que os usuários aceitem o certificado do Skype for Business Server se o domínio SIP da conta de usuário entrar for diferente do nome apresentado no Subject ou Subject Alt Name no certificado. Se o certificado configurado para Skype for Business Server em sua organização não tiver o nome de domínio SIP da conta do sistema de sala Skype em Subject ou Subject Alt Name, você deverá configurar esses domínios apresentados no certificado sob a chave de registro Domínios Confiáveis na máquina de console do Sistema de Sala Skype. O Skype do sistema de sala fornecido Skype Guia do Administrador do Sistema de Sala explica como e onde adicionar domínios confiáveis no cliente Skype for Business sala. 
  
Por exemplo, suponha que os certificados configurados no Skype for Business Server tenham um Nome Alt de Assunto/Assunto de "CONTOSO. LOCAL" e um dos domínios SIP atribuídos a um usuário para o endereço de Skype de login do Sistema de Sala é "confrm1@contoso.net". Como o contoso.net não está no certificado, no computador do sistema de sala Skype, você precisará configurar "contoso.local" como um domínio confiável no Registro, conforme explicado no guia do administrador do sistema de sala Skype fornecido pelo fabricante do Skype Room System. 
  

