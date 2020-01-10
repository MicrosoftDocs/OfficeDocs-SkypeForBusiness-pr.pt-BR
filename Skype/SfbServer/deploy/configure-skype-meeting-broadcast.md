---
title: Configurar sua implantação local para Transmissão de Reunião do Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumo: Saiba mais sobre as etapas que você precisa executar para configurar a transmissão de reunião do Skype para sua implantação híbrida do Skype for Business Server local.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002801"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**Resumo:** Saiba mais sobre as etapas que você precisa executar para configurar a transmissão de reunião do Skype para sua implantação híbrida local do Skype for Business Server.
  
A transmissão de reunião do Skype é um serviço online que faz parte do Office 365. Se você estiver executando o Skype for Business Server no local e quiser usar a transmissão de reunião do Skype no seu ambiente, será necessário seguir as etapas de configuração deste tópico. Antes de começar, o ambiente precisa estar configurado para híbrido com o Skype for Business online. Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar seu ambiente híbrido para a transmissão de reunião do Skype

Você precisará fazer o seguinte para preparar seu ambiente para a transmissão de reunião do Skype:
  
- Configurar a Federação com os recursos do Skype for Business Online
    
- Configurar domínios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar a Federação com os recursos do Skype for Business Online

Para habilitar a Federação com os recursos do Skype for Business Online, você precisa configurar o acesso externo para um provedor de federado SIP. Para fazer isso usando o painel de controle do Skype for Business Server, siga estas etapas:
  
1. Inicie o painel de controle do Skype for Business Server e selecione **acesso externo** à esquerda.
    
2. Selecione **Provedores federados SIP** e clique em **Novo**.
    
3. Configure o novo provedor da seguinte forma:
    
|||
|:-----|:-----|
|**Habilitar comunicações com este provedor:** <br/> |Selecionado  <br/> |
|**Nome do provedor:** <br/> |LyncOnlineResources  <br/> |
|**Serviço de Borda de Acesso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nível de verificação padrão:** <br/> |Permitir que os usuários se comuniquem com todos que usam este provedor.  <br/> |
   
Você também pode habilitar a Federação com os recursos do Skype for Business online executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar domínios federados SIP

Em seguida, você precisa adicionar domínios federados do SIP à lista de domínios permitidos. Repita essas etapas para cada um dos quatro domínios listados, criando quatro novos domínios SIP federados. Esses domínios são para os centros de dados regionais usados no Skype for Business online.
  
1. Inicie o painel de controle do Skype for Business Server e selecione **acesso externo** à esquerda.
    
2. Selecione **Domínios Federados SIP** e clique em **Novo**.
    
3. Para o **Nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Você também pode configurar o acesso externo para domínios federados SIP executando os seguintes cmdlets no Shell de gerenciamento do Skype for Business Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Depois de concluir essas etapas de configuração, você pode começar a usar a transmissão de reunião do Skype na sua implantação. Para obter mais informações sobre a transmissão de reunião do Skype, consulte [o que é uma transmissão de reunião do Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Guia de administração de transmissão de reunião do Skype](https://go.microsoft.com/fwlink/?LinkId=617075).
  

