---
title: Gerenciar políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumo: saiba como gerenciar políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: fc069093b9cc7cf5ce0e1e1f1efc0ee9e18e335d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818642"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Gerenciar políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como gerenciar políticas de conferência no Skype for Business Server.
  
Este tópico descreve como gerenciar as políticas de conferência. Para obter mais informações sobre como planejar e implantar a conferência, consulte [planejar conferências no Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [implantar conferências no Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As políticas de conferência permitem definir uma grande variedade de opções de agendamento e participação, desde se uma reunião pode incluir vídeo e áudio IP até o número máximo de pessoas que podem participar da reunião. Você pode usar políticas de conferência para gerenciar os aspectos legais, de segurança e de banda larga de reuniões.
  
Você pode definir a política de conferência em três níveis: escopo global, escopo de site e escopo de usuário. As configurações se aplicam a um usuário específico desde o menor escopo até o maior. Caso você atribua uma política a um usuário, estas configurações tem precedência. Caso você não atribua uma política de usuário, aplicam-se as definições de site. Caso políticas de usuários ou de site não sejam aplicáveis, a política global fornece as definições padrão.
  
Há uma política global por padrão, portanto você não pode criar uma nova política global. Você também não pode excluir a política global existente, mas pode alterar a política global existente para personalizar suas configurações padrão.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Gerenciar políticas de conferência usando o painel de controle do Skype for Business Server

Para gerenciar as políticas de conferência usando o painel de controle do Skype for Business Server:
  
1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, então, clique em **Política de Conferência**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Gerenciar políticas de conferência usando o Shell de gerenciamento do Skype for Business Server

Para gerenciar reuniões usando o Shell de gerenciamento do Skype for Business Server, use os seguintes cmdlets:
  
**Configurações de política de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Retorna informações sobre as diretivas de conferência que tenham sido configuradas para uso na organização.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Atribui uma diretiva de conferência em escopo por usuário.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Cria uma nova política de conferência para uso na organização.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Remove a diretiva de conferência especificada.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica uma diretiva de conferência existente.  <br/> |
   

