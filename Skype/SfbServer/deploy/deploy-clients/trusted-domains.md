---
title: Domínios confiáveis do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leia este tópico para aprender a configurar domínios confiáveis do Sistema de Salas do Skype e do Skype for Business.
ms.openlocfilehash: 618ea5ce6cd4e12cd1e6a811a065f7a29a5c9ced
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768664"
---
# <a name="skype-room-system-trusted-domains"></a>Domínios confiáveis do Sistema de Salas do Skype
 
Leia este tópico para aprender a configurar domínios confiáveis do Sistema de Salas do Skype e do Skype for Business.
  
## <a name="trusted-domains"></a>Domínios confiáveis

O cliente Skype for Business exibe uma caixa de diálogo que permite que os usuários aceitem o certificado do servidor do Skype for Business se o domínio SIP da conta de usuário que está entrando for diferente do nome apresentado no nome do assunto ou assunto Alt do assunto no certificado. Se o certificado configurado para o Skype for Business Server em sua organização não tiver o nome de domínio SIP da conta do sistema de sala do Skype no assunto ou nome Alt do assunto, você deve configurar esses domínios apresentados no certificado nos domínios confiáveis chave do registro na máquina do console do sistema de sala do Skype. O guia do administrador do seu sistema de salas da Skype, fornecido pelo fabricante, explica como e onde adicionar domínios confiáveis ao cliente Skype for Business. 
  
Por exemplo, suponha que os certificados configurados no Skype for Business Server tenham um nome Alt assunto/assunto de "CONTOSO. LOCAL "e um dos domínios SIP atribuídos a um usuário para o endereço de entrada do sistema de sala do Skype é" confrm1@contoso.net ". Como o contoso.net não está no certificado, na máquina do sistema de sala do Skype, você precisará configurar "contoso. local" como um domínio confiável no registro, conforme explicado no fabricante do seu sistema de salas da Skype guia do administrador do Skype. 
  

