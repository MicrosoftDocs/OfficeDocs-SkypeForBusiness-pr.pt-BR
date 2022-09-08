---
title: licenças Telefonia do Microsoft Teams conta de recurso do Telefonia do Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- admindeeplinkMAC
description: Saiba como atribuir licenças Telefonia do Microsoft Teams Conta de Recurso a contas de recursos para atendedores automáticos e filas de chamadas em sua organização.
ms.openlocfilehash: 56b461c2de32f32dd51d72c5468e31f51b107310
ms.sourcegitcommit: 09b77e83bc41914007606468e322d4ea47e2e8a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "67630421"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>licenças Telefonia do Microsoft Teams conta de recurso do Telefonia do Microsoft Teams

No Microsoft Teams, todos os atendedores automáticos e filas de chamadas exigem uma conta de recurso associada. Cada conta de recurso deve receber uma licença de conta de recurso do Telefonia do Microsoft Teams para garantir que elas sejam identificadas corretamente pelo sistema e funcionem *corretamente,* independentemente de **a** conta de recurso receber um número de telefone. As organizações com uma assinatura que inclui o Telefone do Teams são alocadas automaticamente uma determinada quantidade de licenças da Conta de Recurso de Telefone do **Teams** sem custo adicional.  Um plano de chamada da Microsoft não é necessário, a menos que você queira ser capaz de discar usando essa conta de recurso. Para obter mais informações, consulte [Plan for Teams auto attendant and call queues](../plan-auto-attendant-call-queue.md#prerequisites).

> [!NOTE]
> Anteriormente, uma licença da Conta de Recurso de Telefone do **Teams** (uma vez conhecida como licença de usuário **virtual** ) só era necessária ao atribuir um número de telefone a uma conta de recurso. Agora, todas as contas de recursos devem receber uma licença de Conta de Recurso de Telefone do **Teams** , independentemente de receberem um número de telefone ou não. Além disso, não atribua uma licença **de Telefonia do Teams Padrão** a uma conta de recurso. Se você tiver contas de recursos configuradas com licenças **Telefonia do Teams Padrão**, alterne para uma licença de Conta de Recurso de Telefone do **Teams**, conforme descrito abaixo.
 

## <a name="resource-account-license-allocation"></a>Alocação de licença da Conta de Recurso

Sua organização tem licenças de Conta de Recurso de Telefone **do Teams** alocadas com base em seu tamanho geral. Qualquer organização que tenha uma assinatura com recursos do Sistema de **Telefonia, como o Telefonia do Teams Padrão** e o **Telefone do Teams** com licenças de Plano de Chamada, tem 25 licenças de Conta de Recurso de Telefone do **Teams** disponíveis sem custo. 

Para cada 10 licenças de usuário do **Telefonia do Teams Padrão** ou telefone **do Teams** com Plano de Chamadas em sua organização, mais uma licença de Conta de Recurso de Telefone do **Teams** fica disponível.  A maioria das organizações terá licenças **suficientes da Conta de Recursos** de Telefone do Teams com base nesse plano de dimensionamento. Caso mais licenças da Conta de Recursos de Telefone do **Teams** sejam necessárias, você pode comprar mais licenças da Conta de Recursos de Telefone do **Teams** além da alocação padrão por meio do representante da conta da Microsoft.

### <a name="license-allocation-example"></a>Exemplo de alocação de licença

A Contoso, Inc. comprou 600 licenças que incluem o Sistema de Telefonia (uma para cada funcionário). A Contoso tem uma alocação inicial de 25 mais 60 licenças de Conta de Recurso de Telefone do **Teams** , 85 no total. Sua organização tem 90 filas de chamadas e atendedores automáticos. Eles precisam atribuir todas as licenças da Conta de Recursos de Telefone do **Teams** e comprar cinco licenças adicionais da Conta de Recurso **de Telefone do Teams** . 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Como obter licenças Telefonia do Microsoft Teams conta de recurso

1. Entre [no Centro de administração do Microsoft 365.](https://go.microsoft.com/fwlink/p/?linkid=2024339)
2. Vá para **Complementos de** >  Serviços  > [**de Compra**](https://go.microsoft.com/fwlink/p/?linkid=868433)**de Cobrança**.
3. Role para encontrar a licença **Telefonia do Microsoft Teams Conta de** Recurso. Selecione **Comprar agora**.

   > [!NOTE]
   > Tenha em mente que, mesmo que você esteja dentro de sua alocação, você  ainda deve comprar a licença, embora ela tenha um custo zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Alterar uma conta de recurso existente para usar uma licença Telefonia do Microsoft Teams conta de recurso

Se você tiver contas de recursos existentes usando **uma Telefonia do Teams Padrão**, alterne para usar para uma licença de Conta de Recurso **de Telefone do Teams**:

1. Obtenha a nova licença **da Conta de Recurso de Telefone do Teams** .
2. Siga as etapas vinculadas no Centro de administração do Microsoft 365 mover [usuários para uma assinatura diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Sempre remova uma **licença Telefonia do Teams Padrão** e atribua a licença da Conta de Recurso de Telefone do **Teams** na mesma atividade de licença. Se você remover a licença antiga, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta de recurso poderá não funcionar mais conforme o esperado, como os atendedores automáticos da sua organização e as filas de chamadas não funcionam mais.
>
> Se isso acontecer, recomendamos que você crie uma nova conta de recurso usando a licença da Conta de Recurso de Telefone do **Teams** e remova a conta de recurso interrompida.

## <a name="related-information"></a>Informações relacionadas

[Atualização do serviço Atendedor Automático e Filas de Chamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gerenciar contas de recursos no Microsoft Teams](../manage-resource-accounts.md)
