---
title: Criar ou modificar uma regra de conversão para apresentação de ID do chamador no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumo: saiba como configurar a ID do Chamador usando o painel Skype for Business Server Controle.'
ms.openlocfilehash: 13ca5073956e6cf67264e706a82e63ec72efbac4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865328"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Criar ou modificar uma regra de conversão para apresentação de ID do chamador no Skype for Business Server

**Resumo:** Saiba como configurar a ID do Chamador usando o Painel Skype for Business Server Controle.

Com Skype for Business Server, o número de telefone da parte chamada (ou seja, o número de telefone chamado) pode ser convertido do formato E.164 para o formato de discagem local exigido pelo par de tronco _(ou_ seja, o gateway associado, o PBX (private branch exchange) ou o tronco SIP). Para fazer isso, você deve definir uma ou mais regras de conversão para traduzir o URI de solicitação antes de roteá-lo para o ponto de tronco.

Skype for Business Server também oferece a opção de também traduzir o número de telefone do chamador (ou seja, o número de telefone do qual o chamador está chamando) do formato E.164 para o formato de discagem local exigido pelo ponto de tronco. Por exemplo, você pode criar uma regra de conversão para remover +44 do começo de uma sequência de caracteres de discagem e o substituir por 0144.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Para configurar a ID do Chamador usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.

3. Na página **Configuração do** Tronco, clique duas vezes em um tronco existente (por exemplo, o **tronco Global)** para exibir a caixa de diálogo Editar Configuração **do** Tronco.

4. Para configurar a apresentação da ID do chamador:

   - Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Em **Regras de conversão de número de** chamada, clique nas regras que você deseja associar ao tronco e clique em **OK**.

   - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) na documentação de Implantação.

   - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) na documentação da implantação.

   - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).

   - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

     > [!CAUTION]
     > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.