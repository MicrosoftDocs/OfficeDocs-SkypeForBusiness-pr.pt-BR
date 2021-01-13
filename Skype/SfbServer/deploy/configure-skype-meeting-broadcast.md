---
title: Configurar sua implantação local para a Transmissão de Reunião do Skype
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
description: 'Resumo: saiba mais sobre as etapas que você precisa executar para configurar a Transmissão de Reunião do Skype para sua implantação híbrida local do Skype for Business Server.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820701"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configurar sua implantação local para a Transmissão de Reunião do Skype
 
**Resumo:** Saiba mais sobre as etapas que você precisa realizar para configurar a Transmissão de Reunião do Skype para sua implantação híbrida local do Skype for Business Server.
  
A Transmissão de Reunião do Skype é um serviço online que faz parte do Office 365. Se você estiver executando o Skype for Business Server local e quiser usar a Transmissão de Reunião do Skype em seu ambiente, será necessário seguir as etapas de configuração neste tópico. Antes de começar, seu ambiente precisa ser configurado para híbrido com o Skype for Business Online. Para obter mais informações, consulte Planejar a conectividade híbrida entre o Skype for Business Server e o [Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business [Online.](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Configurar seu ambiente híbrido para a Transmissão de Reunião do Skype

Você precisará fazer o seguinte para preparar seu ambiente para a Transmissão de Reunião do Skype:
  
- Configurar federação com recursos do Skype for Business Online
    
- Configurar domínios sip federados
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Configurar federação com recursos do Skype for Business Online

Para habilitar a federação com os recursos do Skype for Business Online, você precisa configurar o Acesso Externo para um Provedor Federado SIP. Para fazer isso usando o Painel de Controle do Skype for Business Server, siga estas etapas:
  
1. Inicie o Painel de Controle do Skype for Business Server e selecione **Acesso Externo** à esquerda.
    
2. Selecione **Provedores Federados SIP e** clique em **Novo.**
    
3. Configure o novo provedor com as seguintes configurações:
    
|||
|:-----|:-----|
|**Habilita as comunicações com este provedor:** <br/> |Selecionado  <br/> |
|**Nome do provedor:** <br/> |LyncOnlineResources  <br/> |
|**Serviço de Borda de Acesso (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**Nível de verificação padrão:** <br/> |Permitir que os usuários se comuniquem com todos que usam esse provedor.  <br/> |
   
Você também pode habilitar a federação com recursos do Skype for Business Online executando o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Configurar domínios sip federados

Em seguida, você precisa adicionar domínios federados SIP à lista de domínios permitidos. Repita essas etapas para cada um dos domínios listados, criando 4 novos domínios SIP federados. Esses domínios incluem os data centers regionais usados no Skype for Business Online.
  
1. Inicie o Painel de Controle do Skype for Business Server e selecione **Acesso Externo** à esquerda.
    
2. Selecione **Domínios Federados SIP e** clique em **Novo.**
    
3. Para o **nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Você também pode configurar o acesso externo para domínios federados SIP executando os seguintes cmdlets no Shell de Gerenciamento do Skype for Business Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

Depois de concluir essas etapas de configuração, você poderá começar a usar a Transmissão de Reunião do Skype em sua implantação. Para obter mais informações sobre a Transmissão de Reunião do Skype, consulte O que é uma Transmissão de Reunião do [Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) e o Guia de Administração de Transmissão de Reunião [do Skype.](https://go.microsoft.com/fwlink/?LinkId=617075)
  

