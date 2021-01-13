---
title: Gerenciar políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumo: saiba como gerenciar políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835271"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Gerenciar políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como gerenciar políticas de conferência no Skype for Business Server.
  
Este tópico descreve como gerenciar políticas de conferência. Para obter mais informações sobre como planejar e implantar conferências, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As políticas de conferência permitem definir uma ampla variedade de opções de agendamento e participação, desde se uma reunião pode incluir áudio e vídeo IP até o número máximo de pessoas que podem participar. Você pode usar políticas de conferência para gerenciar a segurança, largura de banda e aspectos legais das reuniões.
  
Você pode definir a política de conferência em três níveis: escopo global, escopo de site e escopo de usuário. As configurações se aplicam a um usuário específico desde o menor escopo até o maior. Se você atribuir uma política a um usuário, essas configurações têm precedência. Caso você não atribua uma política de usuário, aplicam-se as definições de site. Caso políticas de usuários ou de site não sejam aplicáveis, a política global fornece as definições padrão.
  
Há uma política global por padrão, portanto você não pode criar uma nova política global. Você também não pode deletar a política global existente, mas pode alterar a política global existente para personalizar suas configurações padrão.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Gerenciar políticas de conferência usando o Painel de Controle do Skype for Business Server

Para gerenciar políticas de conferência usando o Painel de Controle do Skype for Business Server:
  
1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência e** em Política de **Conferência.**
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Gerenciar políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server

Para gerenciar reuniões usando o Shell de Gerenciamento do Skype for Business Server, use os seguintes cmdlets:
  
**Configurações de política de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Retorna informações sobre as diretivas de conferência que tenham sido configuradas para uso na organização.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Atribui uma diretiva de conferência em escopo por usuário.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Cria uma nova política de conferência para uso na organização.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Remove a diretiva de conferência especificada.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica uma diretiva de conferência existente.  <br/> |
   

