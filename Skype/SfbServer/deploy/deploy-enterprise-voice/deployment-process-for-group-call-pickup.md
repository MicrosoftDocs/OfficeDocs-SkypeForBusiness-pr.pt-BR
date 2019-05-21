---
title: Processo de implantação para retirada de chamadas em grupo no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processo de implantação e etapas para o recebimento de chamadas em grupo no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: f493c3c83f3fa703dd5f62989f4f2e444e83ed5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289921"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Processo de implantação para retirada de chamadas em grupo no Skype for Business
 
Processo de implantação e etapas para o recebimento de chamadas em grupo no Skype for Business Server Enterprise Voice.
  
O recurso de recebimento de chamadas em grupo permite que os usuários atendam às chamadas de entrada para seus colegas a partir dos próprios telefones. 
  
 Os componentes que o recurso de retirada de chamadas em grupo usam são instalados e habilitados automaticamente no servidor front-end ou no servidor Standard Edition quando você implanta Enterprise Voice. No entanto, você deve usar as etapas a seguir para configurar o recebimento de chamadas em grupo antes de estar disponível para os usuários.
  
**Processo de implantação do Recebimento de chamada de grupo**

|**Fase**|**Etapas**|**Grupos e funções necessários**|**Documentação de Implantação**|
|:-----|:-----|:-----|:-----|
|Habilitar a ferramenta SEFAUtil em sua topologia|Use o cmdlet New-CsTrustedApplicationPool para criar um novo pool de aplicativos confiáveis. Use o cmdlet New-CsTrustedApplication para especificar a ferramenta SEFAUtil como aplicativo confiável. Execute o cmdlet Enable-CsTopology para habilitar a topologia. Se ainda não o tiver, baixe a versão do Skype for Business Server da ferramenta SEFAUtil deste local e instale-a no pool de aplicativos confiável que você criou na etapa 1. Verifique se o SEFAUtil está executando corretamente ao executá-lo para exibir as configurações de encaminhamento de chamada de um usuário na implantação. |RTCUniversalServerAdmins  <br/> |[Implantar a ferramenta SEFAUtil no Skype for Business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Documentação do recurso ferramentas do kit de recursos do Skype for Business Server 2015](../../management-tools/resource-kit-tools.md). (Para o Skype for Business Server, você deve usar a versão atual da ferramenta, mas esta documentação do Lync Server 2013 ainda se aplica.)  <br/> |
|Configure os intervalos de número para recebimento de chamada na tabela de órbita de estacionamento de chamada  <br/> |Use o cmdlet **New-CSCallParkOrbit** para criar faixas de número de recebimento de chamada na tabela de órbita de estacionamento de chamada e atribua as intervalos de recebimento de chamada ao tipo **GroupPickup**.  <br/> Para uma integração perfeita aos planos de discagem existentes, os intervalos de número são normalmente configurados como um bloco de ramais virtuais. A atribuição dos números de Discagem Direta de Entrada (DID) como números de intervalos  na tabela de órbita de estacionamento de chamada não é suportada.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Criar ou modificar um intervalo de números de tira de chamada em grupo no Skype for Business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Atribuir um número de recebimento de chamadas aos usuários e habilitar o recebimento de chamadas em grupo para os usuários  <br/> |Use o parâmetro/enablegrouppickup na ferramenta do kit de recursos do SEFAUtil para habilitar o recebimento de chamadas em grupo e atribuir um número de recebimento de chamadas para os usuários.  <br/> |-  <br/> |[Habilitar o recebimento de chamadas em grupo para usuários e atribuir um número de grupo no Skype for Business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notifique os usuários do número de recebimento de chamada atribuído e qualquer outro número de interesse  <br/> |Depois de habilitar o recebimento de chamadas em grupo para os usuários, use o email ou algum outro mecanismo para notificá-los do número do grupo de recebimento de chamada. Faça isso para qualquer grupo que os usuários queiram monitorar. Visto que os usuários podem recuperar chamadas de outros usuários mesmo que não estejam no mesmo grupo, é provável que eles precisem do número de vários grupos de recebimento de chamada.  <br/> |-  <br/> ||
|Verificar sua implantação de retirada de chamadas em grupo  <br/> | Teste fazer e receber chamadas para garantir que a configuração funcione conforme o esperado. No mínimo, verifique o seguinte: <br/>  Ligue para um usuário que esteja com o recebimento de chamadas de grupo ativado e tenha outro usuário para recuperar a chamada. O outro usuário pode estar no mesmo grupo, em um grupo diferente ou não estar com o recebimento de chamadas de grupo ativado. <br/>  Ligue para um usuário que esteja com o recebimento de chamadas de grupo ativado e não atende a chamada. <br/> |-  <br/> ||
   

