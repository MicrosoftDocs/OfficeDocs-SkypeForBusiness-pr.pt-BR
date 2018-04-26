---
title: Configurar sua implantação local para Transmissão de Reunião do Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
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
description: 'Resumo: conheça as etapas que você precisa realizar para configurar a  na sua implantação híbrida local do .'
ms.openlocfilehash: e788a263223ea3fa0f4ce9ed844fb5b4eb0ae898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurar sua implantação local para Transmissão de Reunião do Skype
 
Resumo: conheça as etapas que você precisa realizar para configurar a  na sua implantação híbrida local do .
  
A  é um serviço online que faz parte do Office 365. Se você estiver executando o  no local e quiser usar a  no seu ambiente, precisará seguir as etapas de configuração neste tópico. Antes de começar, seu ambiente precisa ser configurado como híbrido no . For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar sua implantação local para Transmissão de Reunião do Skype

É necessário fazer o seguinte para preparar seu ambiente para a :
  
- Configurar federação com o Skype for Business Online
    
- Configurar domínios federados SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar federação com o Skype for Business Online

Para habilitar a federação com recursos do , é necessário configurar Acesso Externo para um Provedor federado SIP. To do this by using the Skype for Business Server Control Panel follow these steps:
  
1. Start the Skype for Business Server Control Panel and select **External Access** on the left.
    
2. Selecione **Provedores federados SIP** e clique em **Novo**.
    
3. Configure o novo provedor da seguinte forma:
    
|||
|:-----|:-----|
|**Habilitar comunicações com este provedor: ** <br/> |Selecionado  <br/> |
|**Nome do provedor:** <br/> |LyncOnlineResources  <br/> |
|**Serviço de Borda de Acesso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nível de verificação padrão:** <br/> |Permitir que os usuários se comuniquem com todos que usam este provedor.  <br/> |
   
You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar domínios federados SIP

Em seguida, você precisa adicionar domínios federados SIP à lista de domínios permitidos. Repita essas etapas para cada um dos quatro domínios listados, criando quatro novos domínios SIP federados. Esses domínios são para os data centers regionais usados no .
  
1. Start the Skype for Business Server Control Panel and select **External Access** on the left.
    
2. Selecione **Domínios Federados SIP** e clique em **Novo**.
    
3. Para o **Nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
Você também pode configurar o acesso externo para domínios federados SIP executando os seguintes cmdlets no :
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "emeameetings.lync.com"
```

```
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "resources.lync.com"
```

Depois de concluir essas etapas de configuração, você pode começar a usar a Transmissão de Reunião do Skype em sua implantação. Para mais informações sobre a Transmissão de Reunião do Skype, consulte [O que é uma Transmissão de Reunião do Skype?](https://go.microsoft.com/fwlink/?LinkId=617071).
  

