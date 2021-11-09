---
title: Habilitar usuários para E9-1-1 em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisões necessárias para a política de local para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários em roaming.
ms.openlocfilehash: 631c74f8ee4d91f1a70f1d2edbfa129602913a6f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844134"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Habilitar usuários para E9-1-1 em Skype for Business Server
 
Decisões necessárias para a política de local para uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários em roaming.
  
Durante o registro do cliente, Skype for Business Server usa uma política de local para configurar as propriedades E9-1-1 para usuários Enterprise Voice habilitados. Esta política contém as configurações que definem como o E9-1-1 é implementado. Por exemplo, a política de local contém informações como a cadeia de caracteres de discagem de emergência e se um usuário precisa ou não inserir manualmente um local se o serviço de Informações de Local não fornecer automaticamente um. Para uma definição completa de uma política de local, consulte [Plan location policies for Skype for Business Server](location-policies.md).
  
Skype for Business Server pode atribuir uma política de local aos clientes com base na sub-rede ou aos usuários com base em uma política global, por site ou por usuário. Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.
  
 **Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**
  
> Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global. No entanto, ao atribuir uma política de local a um site de rede Skype for Business Server e adicionar sub-redes ao site, você pode limitar o suporte do E9-1-1 a locais selecionados dentro da empresa e especificar o comportamento de roteamento E9-1-1 por site. 
    
 **Você planeja habilitar usuários individuais por meio de uma política de usuário?**
  
> Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.
    
 **Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**
  
> Se os usuários são atribuídos a uma política de local global, site ou por usuário, eles podem ser obrigados a inserir manualmente um local no cliente se o cliente não estiver localizado em uma sub-rede definida ou se nenhum local tiver sido encontrado pelo serviço de Informações de Local. Para obter detalhes, [consulte Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).
    

