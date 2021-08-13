---
title: Configurar sua implantação local para a Reunião do Skype Broadcast
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumo: saiba mais sobre as etapas que você precisa executar para configurar Reunião do Skype Transmissão para sua implantação Skype for Business Server híbrida local.'
ms.openlocfilehash: 6cab2ed4fbb5cb2992b970d5a960bbc0ad2e10af2184588aa6c938e9811d2a50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304483"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurar sua implantação local para a Reunião do Skype Broadcast
 
**Resumo:** Saiba mais sobre as etapas que você precisa executar para configurar Reunião do Skype Transmissão para sua implantação Skype for Business Server híbrida local.
  
Reunião do Skype A transmissão é um serviço online que faz parte Office 365. Se você estiver executando Skype for Business Server local e quiser usar a transmissão Reunião do Skype em seu ambiente, você precisará seguir as etapas de configuração neste tópico. Antes de começar, seu ambiente precisa ser configurado para híbrido com Skype for Business Online. Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar seu ambiente híbrido para Reunião do Skype Transmissão

Você precisará fazer o seguinte para preparar seu ambiente para Reunião do Skype Transmissão:
  
- Configurar federação com recursos Skype for Business Online
    
- Configurar domínios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar federação com recursos Skype for Business Online

Para habilitar a federação com Skype for Business online, você precisa configurar o Acesso Externo para um Provedor Federado SIP. Para fazer isso usando o Painel de Controle Skype for Business Server, siga estas etapas:
  
1. Inicie o Skype for Business Server de Controle e selecione **Acesso Externo** à esquerda.
    
2. Selecione **Provedores Federados SIP e** clique em **Novo**.
    
3. Configure o novo provedor com as seguintes configurações:
    
|||
|:-----|:-----|
|**Habilitar comunicações com este provedor:** <br/> |Selecionado  <br/> |
|**Nome do provedor:** <br/> |LyncOnlineResources  <br/> |
|**Serviço de Borda de Acesso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nível de verificação padrão:** <br/> |Permitir que os usuários se comuniquem com todos que usam esse provedor.  <br/> |
   
Você também pode habilitar a federação com Skype for Business online executando o seguinte cmdlet no Shell de Gerenciamento Skype for Business Server:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar domínios federados SIP

Em seguida, você precisa adicionar domínios federados SIP à lista de domínios permitidos. Repita estas etapas para cada um dos domínios listados, criando 4 novos domínios federados SIP. Esses domínios incluem os data centers regionais usados no Skype for Business Online.
  
1. Inicie o Skype for Business Server de Controle e selecione **Acesso Externo** à esquerda.
    
2. Selecione **Domínios Federados SIP** e clique em **Novo**.
    
3. Para o **nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Você também pode configurar o acesso externo para domínios federados SIP executando os seguintes cmdlets no Shell de Gerenciamento Skype for Business Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Depois de concluir essas etapas de configuração, você pode começar a usar Reunião do Skype Transmissão em sua implantação. Para obter mais informações sobre Reunião do Skype Transmissão, consulte O que é uma transmissão Reunião do Skype [transmissão?](https://go.microsoft.com/fwlink/?LinkId=617071) e Reunião do Skype Guia de [Administração de Transmissão.](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)
