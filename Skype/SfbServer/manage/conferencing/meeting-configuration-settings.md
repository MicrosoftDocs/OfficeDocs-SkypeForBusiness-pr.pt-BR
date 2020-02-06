---
title: Gerenciar definições de configuração de reunião no Skype for Business Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumo: saiba como gerenciar as configurações de configuração de reunião no Skype for Business Server.'
ms.openlocfilehash: cefdf304d8cf5ed6ff4560dd5416283d733c3db2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818522"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Gerenciar definições de configuração de reunião no Skype for Business Server
 
**Resumo:** Saiba como gerenciar as configurações de configuração de reunião no Skype for Business Server.
  
Este tópico descreve como gerenciar as definições das configurações de reunião. Para obter mais informações sobre como planejar e implantar a conferência, consulte [planejar conferências no Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [implantar conferências no Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
As definições das configurações de reunião informam o tipo de reuniões que os usuários podem criar, além de controlar como (ou até se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões. Observe que essas configurações só afetam reuniões agendadas; Elas não afetam reuniões ad hoc criadas quando você clica na opção reunir agora no Skype for Business.
  
As definições das configurações de reunião definem o seguinte:
  
- Se os usuários discando de uma rede telefônica pública comutada (PSTN) vão para o lobby
    
- Quem pode ser um apresentador
    
- Se o tipo de conferência é atribuído por padrão
    
- Se usuários anônimos (não autenticados) são admitidos por padrão
    
Você pode definir características de reuniões usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server. 
  
Você pode especificar as configurações de reunião no nível global (criado por padrão), no nível do site ou no nível do pool. Por padrão, as configurações globais definem a experiência de reunião. Se você criar configurações no nível de pool, elas serão aplicadas a todas as reuniões hospedadas pelo pool. Se você não criar configurações no nível de pool, as configurações do nível local serão aplicadas, caso existam. Se você não definir as configurações de nível local, as configurações globais serão aplicadas a todas as reuniões.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gerenciar configurações de reunião usando o painel de controle do Skype for Business Server

Para gerenciar as configurações de reunião usando o painel de controle do Skype for Business Server:
  
1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Conferência**e em **Configuração da reunião**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gerenciar as configurações de reunião usando o Shell de gerenciamento do Skype for Business Server

Para gerenciar reuniões usando o Shell de gerenciamento do Skype for Business Server, use os seguintes cmdlets:
  
**Definições de configuração de reunião**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as definições de configuração de reunião em uso na organização.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de configurações de reunião em escopo do site ou serviço.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Exclui um conjunto existente das configurações de reunião.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica as definições de configuração de reunião em uso na organização.  <br/> |
   

