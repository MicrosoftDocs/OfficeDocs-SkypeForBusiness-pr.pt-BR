---
title: Gerenciar definições de configuração de reuniões no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumo: Aprenda a gerenciar configurações de reunião no Skype para Business Server 2015.'
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Gerenciar definições de configuração de reuniões no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar configurações de reunião no Skype para Business Server 2015.
  
Este tópico descreve como gerenciar as definições das configurações de reunião. Para obter mais informações sobre como planejar e implantar a conferência, consulte [Plan para conferências no Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferência no Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As definições das configurações de reunião informam o tipo de reuniões que os usuários podem criar, além de controlar como (ou até se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões. Observe que essas configurações só afetam reuniões programadas; eles não afetam as reuniões ad hoc criados clicando-se a opção reunir agora Skype para negócios.
  
As definições das configurações de reunião definem o seguinte:
  
- Se os usuários discando de uma rede telefônica pública comutada (PSTN) vão para o lobby
    
- Quem pode ser um apresentador
    
- Se o tipo de conferência é atribuído por padrão
    
- Se usuários anônimos (não autenticados) são admitidos por padrão
    
Você pode definir as características de reuniões usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios. 
  
Você pode especificar configurações no nível global (criada por padrão) da reunião, nível de site ou nível de pool. Por padrão, as configurações globais definem a experiência de reunião. Se você criar configurações no nível de pool, elas serão aplicadas a todas as reuniões hospedadas pelo pool. Se você não criar configurações no nível de pool, as configurações do nível local serão aplicadas, caso existam. Se você não definir as configurações de nível local, as configurações globais serão aplicadas a todas as reuniões.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gerenciar configurações de reunião usando o Skype para o painel de controle do servidor de negócios

Para gerenciar configurações de reunião usando o Skype para o painel de controle do Business Server:
  
1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e em **Configuração da reunião**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gerenciar configurações de reunião usando o Skype do Shell de gerenciamento do servidor de negócios

Para gerenciar reuniões usando Skype do Shell de gerenciamento do servidor de negócios, use os cmdlets a seguir:
  
**Definições de configuração de reunião**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as definições de configuração de reunião em uso na organização.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de configurações de reunião em escopo do site ou serviço.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Exclui um conjunto existente de configurações de reunião.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica as definições de configuração de reunião em uso na organização.  <br/> |
   

