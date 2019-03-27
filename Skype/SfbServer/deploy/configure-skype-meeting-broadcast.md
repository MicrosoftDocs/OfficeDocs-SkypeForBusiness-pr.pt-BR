---
title: Configurar sua implantação local para Transmissão de Reunião do Skype
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumo: Saiba mais sobre as etapas que necessárias para executar para configurar a transmissão do Skype reunião para o seu Skype local para implantação híbrida do Business Server.'
ms.openlocfilehash: 10f09fc31f32e2784bb377ba5fe393e5f13a5618
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896882"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**Resumo:** Saiba mais sobre as etapas que necessárias para executar para configurar a transmissão do Skype reunião para o seu Skype local para implantação híbrida do Business Server.
  
Transmissão do Skype reunião é um serviço online que faz parte do Office 365. Se você estiver executando o Skype para Business Server local e deseja usar a transmissão do Skype reunião em seu ambiente, você precisará siga as etapas de configuração neste tópico. Antes de começar, seu ambiente deve ser configurado para o híbrido com Skype para negócios Online. Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar seu ambiente híbrido para transmissão de reunião do Skype

Você precisará fazer o seguinte para preparar seu ambiente para transmissão do Skype reunião:
  
- Configure a federação do Skype para recursos corporativos Online
    
- Configurar domínios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configure a federação do Skype para recursos corporativos Online

Para habilitar a federação com Skype para recursos corporativos Online, você precisará configurar acesso externo para um provedor federado SIP. Para fazer isso usando o Skype para o painel de controle do Business Server siga estas etapas:
  
1. Inicie o Skype para painel de controle do Business Server e selecione **Acesso externo** à esquerda.
    
2. Selecione **Provedores federados SIP** e clique em **Novo**.
    
3. Configure o novo provedor da seguinte forma:
    
|||
|:-----|:-----|
|**Habilite comunicações com este provedor:** <br/> |Selecionado  <br/> |
|**Nome do provedor:** <br/> |LyncOnlineResources  <br/> |
|**Serviço de Borda de Acesso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nível de verificação padrão:** <br/> |Permitir que os usuários se comuniquem com todos que usam este provedor.  <br/> |
   
Você também pode habilitar a federação com Skype para recursos corporativos Online executando o seguinte cmdlet no Skype do Shell de gerenciamento do servidor de negócios:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar domínios federados SIP

Em seguida, você precisará adicionar domínios SIP federados à lista de domínios permitidos. Repita essas etapas para cada um dos quatro domínios listados, criando quatro novos domínios SIP federados. Incluem esses domínios são para os dados regionais centrais usado no Skype do Business Online.
  
1. Inicie o Skype para painel de controle do Business Server e selecione **Acesso externo** à esquerda.
    
2. Selecione **Domínios Federados SIP** e clique em **Novo**.
    
3. Para o **Nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Você também pode configurar o acesso externo para domínios federados SIP executando os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios:
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Depois de concluir essas etapas de configuração pode começar a usar a transmissão do Skype reunião em sua implantação. Para obter mais informações sobre a transmissão do Skype reunião, consulte [o que é uma transmissão do Skype reunião?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Guia de Admin de transmissão do Skype reunião](https://go.microsoft.com/fwlink/?LinkId=617075).
  

