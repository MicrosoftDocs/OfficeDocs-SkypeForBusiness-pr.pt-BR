---
title: Processo de implantação para atendimento de chamada do grupo no Skype para negócios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processo de implantação e etapas para atendimento de chamada do grupo no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 92dbb6ef4a96ed4972794a61814abcd31586ffb3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884044"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Processo de implantação para atendimento de chamada do grupo no Skype para negócios
 
Processo de implantação e etapas para atendimento de chamada do grupo no Skype para Business Server Enterprise Voice.
  
Atendimento de chamada de grupo permite aos usuários atender chamadas de entrada para seus colegas de suas próprias telefones. 
  
 Os componentes de atendimento de chamada de grupo usa automaticamente estão instalados e ativados no servidor do servidor Front-End ou Standard Edition, de quando você implanta o Enterprise Voice. No entanto, você deve usar as seguintes etapas para configurar o atendimento de chamada de grupo antes de estar disponível aos usuários.
  
**Processo de implantação do Recebimento de chamada de grupo**

|**Fase**|**Etapas**|**Grupos e funções necessários**|**Documentação de Implantação**|
|:-----|:-----|:-----|:-----|
|Habilitar a ferramenta de SEFAUtil em sua topologia|Use o cmdlet New-CsTrustedApplicationPool para criar um novo pool de aplicativos confiáveis. Use o cmdlet New-CsTrustedApplication para especificar a ferramenta SEFAUtil como aplicativo confiável. Execute o cmdlet Enable-CsTopology para habilitar a topologia. Se você ainda não tivê-lo, baixe o Skype para Business Server versão da ferramenta SEFAUtil deste local e instalá-lo em um pool de aplicativos confiáveis que você criou na etapa 1. Verifique se o SEFAUtil está executando corretamente ao executá-lo para exibir as configurações de encaminhamento de chamada de um usuário na implantação. |RTCUniversalServerAdmins  <br/> |[Implantar a ferramenta de SEFAUtil em Skype para negócios](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentação de ferramentas do Skype para Business Server 2015 Resource Kit](../../management-tools/resource-kit-tools.md). (Para Skype para Business Server, você deve usar a versão atual da ferramenta, mas ainda aplica esta documentação do Lync Server 2013).  <br/> |
|Configure os intervalos de número para recebimento de chamada na tabela de órbita de estacionamento de chamada  <br/> |Use o cmdlet **New-CSCallParkOrbit** para criar faixas de número de recebimento de chamada na tabela de órbita de estacionamento de chamada e atribua as intervalos de recebimento de chamada ao tipo **GroupPickup**.  <br/> Para uma integração perfeita aos planos de discagem existentes, os intervalos de número são normalmente configurados como um bloco de ramais virtuais. A atribuição dos números de Discagem Direta de Entrada (DID) como números de intervalos  na tabela de órbita de estacionamento de chamada não é suportada.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para negócios](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Atribuir um número de retirada de chamada aos usuários e habilite o atendimento de chamada de grupo para os usuários  <br/> |Use o parâmetro /enablegrouppickup na ferramenta do kit de recursos do SEFAUtil para habilitar o atendimento de chamada de grupo e atribuir um número de retirada de chamada para usuários.  <br/> |-  <br/> |[Habilitar o atendimento de chamada de grupo para usuários e atribuir um número de grupo no Skype para negócios](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notifique os usuários do número de recebimento de chamada atribuído e qualquer outro número de interesse  <br/> |Depois de habilitar o recebimento de chamadas em grupo para os usuários, use o email ou algum outro mecanismo para notificá-los do número do grupo de recebimento de chamada. Faça isso para qualquer grupo que os usuários queiram monitorar. Visto que os usuários podem recuperar chamadas de outros usuários mesmo que não estejam no mesmo grupo, é provável que eles precisem do número de vários grupos de recebimento de chamada.  <br/> |-  <br/> ||
|Verifique se a sua implantação de atendimento de chamada de grupo  <br/> | Teste fazer e receber chamadas para garantir que a configuração funcione conforme o esperado. No mínimo, verifique o seguinte: <br/>  Ligue para um usuário que esteja com o recebimento de chamadas de grupo ativado e tenha outro usuário para recuperar a chamada. O outro usuário pode estar no mesmo grupo, em um grupo diferente ou não estar com o recebimento de chamadas de grupo ativado. <br/>  Ligue para um usuário que esteja com o recebimento de chamadas de grupo ativado e não atende a chamada. <br/> |-  <br/> ||
   

