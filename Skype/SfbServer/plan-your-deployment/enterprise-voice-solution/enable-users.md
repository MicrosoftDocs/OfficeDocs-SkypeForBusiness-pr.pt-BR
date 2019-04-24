---
title: Habilitar usuários para E9-1-1 em Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisões necessárias para a política de local para uma implantação do E9-1-1 em Skype para Business Server Enterprise Voice, incluindo quais usuários habilitem e como dar suporte a usuários móveis.
ms.openlocfilehash: 57a84d18bec0547f1179e62013c9b957afdd2c53
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206919"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Habilitar usuários para E9-1-1 em Skype para Business Server
 
Decisões necessárias para a política de local para uma implantação do E9-1-1 em Skype para Business Server Enterprise Voice, incluindo quais usuários habilitem e como dar suporte a usuários móveis.
  
Durante o registro de cliente, Skype para Business Server usa uma política de local para configurar as propriedades de E9-1-1 para usuários habilitados para o Enterprise Voice. Esta política contém as configurações que definem como o E9-1-1 é implementado. Por exemplo, a política de local contém informações como cadeia de caracteres de discagem de emergência e independentemente de um usuário precisa digitar um local manualmente, se o serviço de informações de local não ocorra automaticamente ou não fornecer um. Para obter uma definição completa de uma política de local, consulte [planejar políticas de local para Skype para Business Server](location-policies.md).
  
Skype para Business Server pode atribuir uma política de local para clientes baseados em sub-rede ou para usuários com base em global, cada site ou política por usuário. Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.
  
 **Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**
  
> Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global. No entanto, atribuindo uma política de local a um Skype para o site de rede do servidor de negócios e, em seguida, adicionando sub-redes ao site, você pode limitar o suporte do E9-1-1 a locais selecionados na empresa e especificar o comportamento de roteamento do E9-1-1 em uma base por site. 
    
 **Você planeja habilitar usuários individuais por meio de uma política de usuário?**
  
> Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.
    
 **Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**
  
> Se os usuários recebem um global, site, ou política de local por usuário, podem ser necessários para digitar manualmente um local ao cliente se o cliente não estiver localizado dentro de uma sub-rede definida ou nenhum local foi encontrado pelo serviço de informações de local. Para obter detalhes, consulte [Define a experiência do usuário para adquirir manualmente um local no Skype para Business Server](manually-acquiring-a-location.md).
    

