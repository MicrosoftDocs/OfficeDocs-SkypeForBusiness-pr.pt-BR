---
title: Gerenciar configurações de reunião no Skype for Business Server
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
description: 'Resumo: Saiba como gerenciar as configurações de reunião no Skype for Business Server.'
ms.openlocfilehash: 1e6ef11992a547456d2a971c2f8de6f3097b166e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119430"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Gerenciar configurações de reunião no Skype for Business Server
 
**Resumo:** Saiba como gerenciar as configurações de reunião no Skype for Business Server.
  
Este tópico descreve como gerenciar as configurações de reunião. Para obter mais informações sobre como planejar e implantar a conferência, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As configurações de reunião determinam o tipo de reuniões que os usuários podem criar, além de controlar como (ou mesmo se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões. Observe que essas configurações afetam apenas reuniões agendadas; eles não afetam reuniões ad hoc criadas clicando na opção Reunir Agora no Skype for Business.
  
As configurações de reunião definem o seguinte:
  
- Se os usuários que estão discando da rede pública (PSTN) vão para o lobby
    
- Quem pode ser um apresentador
    
- Se o tipo de conferência é atribuído por padrão
    
- Se os usuários anônimos (não autenticados) são admitidos por padrão
    
Você pode definir características de reuniões usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server. 
  
Você pode especificar as configurações de reunião no nível global (criado por padrão), no nível do site ou no nível do pool. Por padrão, as configurações globais definem a experiência de reunião. Se você criar configurações a nível de pool, elas se aplicarão a todas as reuniões hospedadas pelo pool. Se você não criar configurações a nível de pool, as configurações a nível local serão aplicadas, caso existam. Se você não definir as configurações a nível local, as configurações globais serão aplicadas a todas as reuniões.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gerenciar configurações de reunião usando o Painel de Controle do Skype for Business Server

Para gerenciar as configurações de reunião usando o Painel de Controle do Skype for Business Server:
  
1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique **em Conferência** e em **Configuração de Reunião.**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gerenciar configurações de reunião usando o Shell de Gerenciamento do Skype for Business Server

Para gerenciar reuniões usando o Shell de Gerenciamento do Skype for Business Server, use os seguintes cmdlets:
  
**Definições de configuração de reunião**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as configurações de reunião atualmente em uso em sua organização.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Cria um novo conjunto de configurações de reunião em escopo do local ou serviço.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Exclui uma coleção existente de configurações de reunião.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica as configurações de reunião atualmente em uso em sua organização.  <br/> |
