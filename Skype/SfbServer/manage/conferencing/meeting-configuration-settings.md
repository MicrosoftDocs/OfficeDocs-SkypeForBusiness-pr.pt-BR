---
title: Gerenciar definições de configuração de reunião no Skype for Business Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumo: Saiba como gerenciar as definições de configuração de reunião no Skype for Business Server.'
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828081"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Gerenciar definições de configuração de reunião no Skype for Business Server
 
**Resumo:** Saiba como gerenciar as definições de configuração de reunião no Skype for Business Server.
  
Este tópico descreve como gerenciar as definições de configuração de reunião. Para obter mais informações sobre como planejar e implantar conferências, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As definições de configuração de reunião ditam o tipo de reuniões que os usuários podem criar, além de controlar como (ou até mesmo se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões. Observe que essas configurações afetam apenas reuniões agendadas; elas não afetam as reuniões ad-hoc criadas clicando na opção Reunir Agora no Skype for Business.
  
As definições de configuração de reunião definem o seguinte:
  
- Se os usuários que estão discando da rede pública (PSTN) vão para o lobby
    
- Quem pode ser um apresentador
    
- Se o tipo de conferência é atribuído por padrão
    
- Se os usuários anônimos (não autenticados) são admitidos por padrão
    
Você pode definir as características das reuniões usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server. 
  
Você pode especificar as configurações de reunião no nível global (criado por padrão), no nível do site ou no nível do pool. Por padrão, as configurações globais definem a experiência da reunião. Se você criar configurações a nível de pool, elas se aplicarão a todas as reuniões hospedadas pelo pool. Se você não criar configurações a nível de pool, as configurações a nível local serão aplicadas, caso existam. Se você não definir as configurações a nível local, as configurações globais serão aplicadas a todas as reuniões.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gerenciar configurações de reunião usando o Painel de Controle do Skype for Business Server

Para gerenciar configurações de reunião usando o Painel de Controle do Skype for Business Server:
  
1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência e** em Configuração de **Reunião.**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gerenciar configurações de reunião usando o Shell de Gerenciamento do Skype for Business Server

Para gerenciar reuniões usando o Shell de Gerenciamento do Skype for Business Server, use os seguintes cmdlets:
  
**Definições de configuração de reunião**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as definições de configuração de reunião em uso na organização.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Cria um novo conjunto de configurações de reunião em escopo do local ou serviço.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Exclui um conjunto existente de definições de configuração de reunião.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica as definições de configuração de reunião em uso na organização.  <br/> |
   

