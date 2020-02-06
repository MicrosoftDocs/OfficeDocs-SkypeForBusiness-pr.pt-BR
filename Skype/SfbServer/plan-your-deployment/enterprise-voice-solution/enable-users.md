---
title: Habilitar usuários para o E9-1-1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisões necessárias para a política de localização de uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários móveis.
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802951"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Habilitar usuários para o E9-1-1 no Skype for Business Server
 
Decisões necessárias para a política de localização de uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários móveis.
  
Durante o registro do cliente, o Skype for Business Server usa uma política de localização para configurar as propriedades E9-1-1 para usuários habilitados para Enterprise Voice. Esta política contém as configurações que definem como o E9-1-1 é implementado. Por exemplo, a política de localização contém informações como a cadeia de caracteres de discagem de emergência e se um usuário precisa ou não inserir um local manualmente se o serviço de informações de localização não fornecer uma conta automaticamente. Para obter uma definição completa de uma política de localização, consulte [planejar políticas de localização para o Skype for Business Server](location-policies.md).
  
O Skype for Business Server pode atribuir uma política de localização a clientes com base na sub-rede ou aos usuários com base em políticas globais, por site ou por usuário. Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.
  
 **Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**
  
> Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global. No entanto, ao atribuir uma política de localização a um site de rede do Skype for Business Server e adicionar sub-redes ao site, você pode limitar o suporte a E9-1 a locais selecionados dentro da empresa e especificar o comportamento de roteamento E9-1-1 por site. 
    
 **Você planeja habilitar usuários individuais por meio de uma política de usuário?**
  
> Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.
    
 **Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**
  
> Se os usuários forem atribuídos a uma política de local global, de site ou por usuário, eles poderão ser solicitados a inserir um local manualmente no cliente se o cliente não estiver localizado dentro de uma sub-rede definida ou se nenhum local tiver sido encontrado pelo serviço informações de localização. Para obter detalhes, consulte [definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server](manually-acquiring-a-location.md).
    

