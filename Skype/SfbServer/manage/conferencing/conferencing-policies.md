---
title: Gerenciar políticas de conferência no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumo: Saiba como gerenciar políticas de conferência do Skype para Business Server 2015.'
ms.openlocfilehash: 48ae623a9571b848ccb70b377416343eccca0c1c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-policies-in-skype-for-business-server-2015"></a>Gerenciar políticas de conferência no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar políticas de conferência do Skype para Business Server 2015.
  
Este tópico descreve como gerenciar as políticas de conferência. Para obter mais informações sobre como planejar e implantar a conferência, consulte [Plan para conferências no Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferência no Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As políticas de conferência permitem definir uma grande variedade de opções de agendamento e participação, desde se uma reunião pode incluir vídeo e áudio IP até o número máximo de pessoas que podem participar da reunião. Você pode usar políticas de conferência para gerenciar os aspectos legais, de segurança e de banda larga de reuniões.
  
Você pode definir a política de conferência em três níveis: escopo global, escopo de site e escopo de usuário. As configurações se aplicam a um usuário específico desde o menor escopo até o maior. Caso você atribua uma política a um usuário, estas configurações tem precedência. Caso você não atribua uma política de usuário, aplicam-se as definições de site. Caso políticas de usuários ou de site não sejam aplicáveis, a política global fornece as definições padrão.
  
Há uma política global por padrão, portanto você não pode criar uma nova política global. Você também não pode excluir a política global existente, mas pode alterar a política global existente para personalizar suas configurações padrão.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Gerenciar políticas de conferência usando o Skype para painel de controle do servidor de negócios

Para gerenciar diretivas de conferência usando Skype para o painel de controle do Business Server:
  
1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, então, clique em **Política de Conferência**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Gerenciar políticas de conferência usando o Skype do Shell de gerenciamento do servidor de negócios

Para gerenciar reuniões usando Skype do Shell de gerenciamento do servidor de negócios, use os cmdlets a seguir:
  
**Configurações de política de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Retorna informações sobre as diretivas de conferência que tenham sido configuradas para uso na organização.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Atribui uma diretiva de conferência em escopo por usuário.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Cria uma nova política de conferência para uso na organização.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Remove a diretiva de conferência especificada.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica uma diretiva de conferência existente.  <br/> |
   

