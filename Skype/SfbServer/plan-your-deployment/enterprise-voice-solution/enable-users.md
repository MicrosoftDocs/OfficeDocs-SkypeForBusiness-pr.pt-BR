---
title: Habilitar usuários para E9-1-1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Decisões necessárias para a política de local para uma implantação de E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários em roaming.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825741"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Habilitar usuários para E9-1-1 no Skype for Business Server
 
Decisões necessárias para a política de local para uma implantação de E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários em roaming.
  
Durante o registro do cliente, o Skype for Business Server usa uma política de local para configurar as propriedades do E9-1-1 para usuários habilitados para Enterprise Voice. Esta política contém as configurações que definem como o E9-1-1 é implementado. Por exemplo, a política de local contém informações como a cadeia de caracteres de discagem de emergência e se um usuário precisa ou não inserir manualmente um local se o serviço de Informações de Local não fornecer um automaticamente. Para uma definição completa de uma política de local, consulte Planejar políticas [de local para o Skype for Business Server.](location-policies.md)
  
O Skype for Business Server pode atribuir uma política de local a clientes com base em sub-rede ou a usuários com base em uma política global, por site ou por usuário. Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.
  
 **Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**
  
> Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global. No entanto, ao atribuir uma política de local a um site de rede do Skype for Business Server e adicionar sub-redes ao site, você pode limitar o suporte do E9-1-1 a locais selecionados dentro da empresa e especificar o comportamento de roteamento E9-1-1 por site. 
    
 **Você planeja habilitar usuários individuais por meio de uma política de usuário?**
  
> Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.
    
 **Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**
  
> Se os usuários são atribuídos a uma política de local global, por site ou por usuário, eles podem ser obrigados a inserir manualmente um local no cliente se o cliente não está localizado dentro de uma sub-rede definida ou se nenhum local foi encontrado pelo serviço de Informações de Local. Para obter detalhes, [consulte Definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server.](manually-acquiring-a-location.md)
    

