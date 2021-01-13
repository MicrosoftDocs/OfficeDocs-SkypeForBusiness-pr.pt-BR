---
title: Criar ou modificar uma regra de conversão para apresentação de ID de chamadas no Skype for Business Server
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
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumo: Saiba como configurar a ID de chamadas usando o Painel de Controle do Skype for Business Server.'
ms.openlocfilehash: ca1451a051a1c9053b88861222d2c4d42c5d555b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804181"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Criar ou modificar uma regra de conversão para apresentação de ID de chamadas no Skype for Business Server

**Resumo:** Saiba como configurar a ID de chamadas usando o Painel de Controle do Skype for Business Server.

Com o Skype for Business Server, o número de telefone da parte chamada (ou seja, o número de telefone chamado) pode ser convertido do formato E.164 para o formato de discagem local exigido pelo par de tronco  _(ou_ seja, o gateway associado, PBX (central privada de comutamento) ou tronco SIP). Para fazer isso, você deve definir uma ou mais regras de conversão para traduzir o URI de Solicitação antes de roteá-lo para o ponto de tronco.

O Skype for Business Server também oferece a opção de converter também o número de telefone do chamador (ou seja, o número de telefone do qual o chamador está ligando) do formato E.164 para o formato de discagem local exigido pelo ponto do tronco. Por exemplo, você pode criar uma regra de conversão para remover +44 do começo de uma sequência de caracteres de discagem e o substituir por 0144.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Para configurar a ID de chamadas usando o Painel de Controle do Skype for Business Server

1. Abra o Painel de Controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.

3. Na página **Configuração do** Tronco, clique duas vezes em um tronco existente (por exemplo, o tronco **Global)** para exibir a caixa de diálogo Editar **Configuração** do Tronco.

4. Para configurar a apresentação da ID de chamada:

   - Para escolher uma ou mais regras de uma lista de todas as regras de conversão disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Em **Regras de conversão de** número de chamada, clique nas regras que você deseja associar ao tronco e clique em **OK.**

   - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.

   - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) na documentação da implantação.

   - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

     > [!CAUTION]
     > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.


