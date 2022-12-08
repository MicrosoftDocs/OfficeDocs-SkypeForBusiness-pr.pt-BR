---
title: Telefonia do Microsoft Teams licenças da Conta de Recursos
author: DaniEASmith
ms.author: danismith
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
description: Saiba como atribuir licenças Telefonia do Microsoft Teams Conta de Recursos a contas de recurso para atendentes automáticos e filas de chamadas em sua organização.
ms.openlocfilehash: d3eacab8569981550520385c4aee297ae6835a59
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307756"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Telefonia do Microsoft Teams licenças da Conta de Recursos

No Microsoft Teams, todos os atendentes automáticos e filas de chamadas exigem uma conta de recurso associada. Cada conta de recurso deve receber uma **licença Telefonia do Microsoft Teams Conta de Recursos** para garantir que elas sejam identificadas corretamente pelo sistema e funcionem corretamente, *independentemente de a conta de recurso receber um número de telefone*. Organizações com uma assinatura que inclui o Teams Phone são alocadas automaticamente uma determinada quantidade de licenças da **Conta de Recursos do Teams Phone** sem nenhum custo adicional.  Um plano de chamada Microsoft não é necessário, a menos que você queira ser capaz de discar usando essa conta de recurso. Para obter mais informações, consulte [Planejar filas de chamadas e atendimento automático do Teams](../plan-auto-attendant-call-queue.md#prerequisites).

> [!NOTE]
> Anteriormente, uma licença **da Conta de Recursos de Telefone do Teams** (antes conhecida como licença de **usuário virtual** ) só era necessária ao atribuir um número de telefone a uma conta de recurso. Agora, todas as contas de recurso devem receber uma licença da **Conta de Recursos do Teams Phone** , independentemente de receberem um número de telefone ou não. Além disso, não atribua uma licença **de Telefonia do Teams Padrão** a uma conta de recurso. Se atualmente você tiver contas de recurso configuradas com **licenças de Telefonia do Teams Padrão**, deverá alternar para uma licença **de Conta de Recurso do Teams Phone**, conforme descrito abaixo.
 

## <a name="resource-account-license-allocation"></a>Alocação de licença da Conta de Recurso

Sua organização está alocada em licenças da **Conta de Recursos de Telefone do Teams** com base no tamanho geral. Qualquer organização que tenha uma assinatura com recursos do Sistema telefônico, como **Telefonia do Teams Padrão** e **Teams Phone com licenças de Plano de Chamada**, está alocada 25 licenças da **Conta de Recursos de Telefone do Teams** disponíveis sem nenhum custo. 

Para cada 10 licenças de usuário do **Telefonia do Teams Padrão** ou **do Teams Phone com o Plano de Chamada** em sua organização, mais uma licença da **Conta de Recursos de Telefone do Teams** fica disponível.  A maioria das organizações terá licenças suficientes da **Conta de Recursos do Teams Phone** com base neste plano de dimensionamento. Caso mais licenças da **Conta de Recursos do Teams Phone** sejam necessárias, você poderá comprar mais licenças da **Conta de Recursos do Teams Phone** além da alocação padrão por meio de EA, EAS, EES, CSP, Web Direct, NCE – led do cliente e NCE – parceiro liderado ou seu representante da conta Microsoft.

### <a name="license-allocation-example"></a>Exemplo de alocação de licença

A Contoso, Inc. comprou 600 licenças que incluem o Sistema telefônico (uma para cada funcionário). A Contoso está alocada em 25 mais 60 licenças de **Conta de Recursos de Telefone do Teams** , 85 no total. Sua organização tem 90 filas de chamadas e atendentes automáticos. Eles precisam atribuir todas as licenças da **Conta de Recursos de Telefone do Teams** e comprar cinco licenças extras **da Conta de Recursos de Telefone do Teams** . 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Como obter licenças Telefonia do Microsoft Teams Conta de Recursos

1. Entre no [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Acesse **Complementos de Serviços** >  de [**Compra**](https://go.microsoft.com/fwlink/p/?linkid=868433)de **Cobrança** > .
3. Role para encontrar a **licença Telefonia do Microsoft Teams Conta de Recursos**. Selecione **Comprar agora**.

   > [!NOTE]
   > Tenha em mente que, mesmo que você esteja dentro de sua alocação, você ainda deve **comprar** a licença, mesmo que ela tenha um custo zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Alterar uma conta de recurso existente para usar uma licença da Conta de Recurso Telefonia do Microsoft Teams

Se você tiver contas de recursos existentes usando uma licença **Telefonia do Teams Padrão**, deverá alternar para usar para uma licença **da Conta de Recursos do Teams Phone**:

1. Obtenha a nova licença **de Conta de Recurso de Telefone do Teams** .
2. Siga as etapas vinculadas no Centro de administração do Microsoft 365 para [Mover usuários para uma assinatura diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Sempre remova uma licença **Telefonia do Teams Padrão** e atribua a licença **conta de recursos do Teams Phone** na mesma atividade de licença. Se você remover a licença antiga, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta de recursos poderá não funcionar mais conforme o esperado, como os atendentes automáticos da sua organização e as filas de chamadas não funcionando mais.
>
> Se isso acontecer, recomendamos que você crie uma nova conta de recurso usando a licença **da Conta de Recursos do Teams Phone** e remova a conta de recurso quebrada.

## <a name="related-information"></a>Informações relacionadas

[Atualização do serviço de atendimento automático e filas de chamada](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gerenciar contas de recursos no Microsoft Teams](../manage-resource-accounts.md)
