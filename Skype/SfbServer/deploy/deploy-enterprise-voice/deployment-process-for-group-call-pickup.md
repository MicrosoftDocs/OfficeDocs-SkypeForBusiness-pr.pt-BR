---
title: Processo de implantação do Recebimento de Chamadas em Grupo no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processo de implantação e etapas para atendimento de chamada do grupo no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: ac061844e38ac435cf84d3972cf24a6eca085f57
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business-2015"></a>Deployment process for Group Call Pickup in Skype for Business 2015
 
Processo de implantação e etapas para atendimento de chamada do grupo no Skype para Business Server Enterprise Voice.
  
Atendimento de chamada de grupo permite aos usuários atender chamadas de entrada para seus colegas de suas próprias telefones. 
  
 Os componentes de atendimento de chamada de grupo usa automaticamente estão instalados e ativados no servidor do servidor Front-End ou Standard Edition, de quando você implanta o Enterprise Voice. No entanto, você deve usar as seguintes etapas para configurar o atendimento de chamada de grupo antes de estar disponível aos usuários.
  
**Processo de implantação de retirada de chamada de grupo**

|**Fase**|**Etapas**|**Grupos e funções necessários**|**Documentação de implantação**|
|:-----|:-----|:-----|:-----|
|Habilitar a ferramenta de SEFAUtil em sua topologia  <br/> |
Use o cmdlet New-CsTrustedApplicationPool para criar um novo pool de aplicativos confiáveis. Use o cmdlet New-CsTrustedApplication para especificar a ferramenta SEFAUtil como aplicativo confiável. Execute o cmdlet Enable-CsTopology para habilitar a topologia. Se você ainda não tivê-lo, baixe o Skype para Business Server versão da ferramenta SEFAUtil deste local e instalá-lo em um pool de aplicativos confiáveis que você criou na etapa 1. Verifique se o SEFAUtil está executando corretamente ao executá-lo para exibir as configurações de encaminhamento de chamada de um usuário na implantação. |RTCUniversalServerAdmins  <br/> |[Implantar a ferramenta de SEFAUtil em Skype para negócios 2015](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool.](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps) [Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentação de ferramenta do kit de recursos do Lync Server 2013](https://technet.microsoft.com/en-us/library/jj945604%28v=ocs.15%29.aspx). (Para Skype para Business Server, você deve usar a versão atual da ferramenta, mas esta documentação do Lync Server 2013 ainda se aplica.  <br/> |
|Configure os intervalos de número para recebimento de chamada na tabela de órbita de estacionamento de chamada  <br/> |Use o cmdlet **New-CSCallParkOrbit** para criar intervalos de números retirada de chamada na tabela de órbita de estacionamento de chamada e atribuir os intervalos de retirada de chamada do tipo **GroupPickup**.  <br/> Para uma integração perfeita aos planos de discagem existentes, os intervalos de número são normalmente configurados como um bloco de ramais virtuais. A atribuição dos números de Discagem Direta de Entrada (DID) como números de intervalos  na tabela de órbita de estacionamento de chamada não é suportada.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para negócios 2015](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Atribuir um número de retirada de chamada aos usuários e habilite o atendimento de chamada de grupo para os usuários  <br/> |Use o parâmetro /enablegrouppickup na ferramenta do kit de recursos do SEFAUtil para habilitar o atendimento de chamada de grupo e atribuir um número de retirada de chamada para usuários.  <br/> |-  <br/> |[Habilitar o atendimento de chamada de grupo para usuários e atribuir um número de grupo no Skype para negócios 2015](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notifique os usuários do número de recebimento de chamada atribuído e qualquer outro número de interesse  <br/> |Depois de habilitar o recebimento de chamadas em grupo para os usuários, use o email ou algum outro mecanismo para notificá-los do número do grupo de recebimento de chamada. Faça isso para qualquer grupo que os usuários queiram monitorar. Visto que os usuários podem recuperar chamadas de outros usuários mesmo que não estejam no mesmo grupo, é provável que eles precisem do número de vários grupos de recebimento de chamada.  <br/> |-  <br/> ||
|Verifique se a sua implantação de atendimento de chamada de grupo  <br/> | Teste fazer e receber chamadas para garantir que a configuração funcione conforme o esperado. No mínimo, verifique o seguinte: <br/>  Ligue para um usuário que esteja com o recebimento de chamadas de grupo ativado e tenha outro usuário para recuperar a chamada. O outro usuário pode estar no mesmo grupo, em um grupo diferente ou não estar com o recebimento de chamadas de grupo ativado. <br/>  Ligue para um usuário que esteja com o recebimento de chamadas de grupo ativado e não atende a chamada. <br/> |-  <br/> ||
   

