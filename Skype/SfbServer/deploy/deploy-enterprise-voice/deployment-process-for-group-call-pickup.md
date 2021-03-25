---
title: Processo de implantação para coleta de chamadas em grupo no Skype for Business
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Processo de implantação e etapas para Coleta de Chamadas de Grupo no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 44f161b72661bb6bdaf52c88448df23546439be1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105787"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Processo de implantação para coleta de chamadas em grupo no Skype for Business
 
Processo de implantação e etapas para Coleta de Chamadas de Grupo no Skype for Business Server Enterprise Voice.
  
O Recebimento de Chamadas de Grupo permite que os usuários atendam a chamadas de entrada para seus colegas de seus próprios telefones. 
  
 Os componentes que a Coleta de Chamada de Grupo usa são instalados e habilitados automaticamente no Servidor Front-End ou no servidor Standard Edition quando você implanta Enterprise Voice. No entanto, você deve usar as etapas a seguir para configurar o Atendimento de Chamada de Grupo antes de ele estar disponível para os usuários.
  
**Processo de implantação de retirada de chamada de grupo**

|**Fase**|**Etapas**|**Grupos e funções exigidos**|**Documentação de Implantação**|
|:-----|:-----|:-----|:-----|
|Habilitar a ferramenta SEFAUtil em sua topologia|Use o cmdlet New-CsTrustedApplicationPool para criar um novo pool de aplicativos confiáveis. Use o cmdlet New-CsTrustedApplication para especificar a ferramenta SEFAUtil como aplicativo confiável. Execute o cmdlet Enable-CsTopology para habilitar a topologia. Se você ainda não a tiver, baixe a versão do Skype for Business Server da ferramenta SEFAUtil deste local e instale-a no pool de aplicativos confiáveis que você criou na etapa 1. Verifique se SEFAUtil está sendo executado corretamente executando-o para exibir as configurações de encaminhamento de chamada de um usuário na implantação. |RTCUniversalServerAdmins  <br/> |[Implantar a ferramenta SEFAUtil no Skype for Business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> Documentação das Ferramentas de Kit de Recursos do [Skype for Business Server 2015.](../../management-tools/resource-kit-tools.md) (Para o Skype for Business Server, você deve usar a versão atual da ferramenta, mas essa documentação do Lync Server 2013 ainda se aplica.)  <br/> |
|Configurar intervalos de números de retirada de chamada na tabela de órbita do estacionamento de chamada  <br/> |Use o cmdlet **New-CSCallParkOrbit** para criar intervalos de números de atendimento de chamadas na tabela de órbita do estacionamento de chamada e atribuir aos intervalos de retirada de chamada o tipo **GroupPickup**.  <br/> Para uma integração perfeita com planos de discagem existentes, intervalos de números geralmente são configurados como um bloco de extensões virtuais. Não há suporte para a atribuição de números did (discagem direta interna) como números de intervalo na tabela de órbita do estacionamento de chamada.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Criar ou modificar um intervalo de números de Retirada de Chamadas de Grupo no Skype for Business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Atribuir um número de retirada de chamada aos usuários e habilitar o Atendimento de Chamada de Grupo para os usuários  <br/> |Use o parâmetro /enablegrouppickup na ferramenta de kit de recursos SEFAUtil para habilitar a Coleta de Chamada de Grupo e atribuir um número de retirada de chamada para os usuários.  <br/> |-  <br/> |[Habilitar o Atendimento de Chamadas de Grupo para usuários e atribuir um número de grupo no Skype for Business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Notificar os usuários sobre o número de retirada de chamada atribuído e qualquer outro número de interesse  <br/> |Depois de habilitar a Coleta de Chamada de Grupo para usuários, use email ou algum outro mecanismo para notificar os usuários do número do grupo de retirada de chamada. Notifique os usuários do número do grupo de retirada de chamada para qualquer grupo que eles possam querer monitorar. Como os usuários podem recuperar chamadas para outros usuários mesmo se não estão no mesmo grupo, os usuários podem precisar do número do grupo de retirada de chamadas para vários grupos.  <br/> |-  <br/> ||
|Verificar sua implantação de Retirada de Chamada de Grupo  <br/> | Teste a colocação e recuperação de chamadas para garantir que sua configuração funcione conforme o esperado. No mínimo, verifique o seguinte: <br/>  Chame um usuário habilitado para o Atendimento de Chamada de Grupo e que outro usuário recupere a chamada. O outro usuário pode estar no mesmo grupo, em um grupo diferente ou não ter a Retirada de Chamada de Grupo habilitada. <br/>  Chame um usuário habilitado para o Atendimento de Chamada de Grupo e não atenda à chamada. <br/> |-  <br/> ||
