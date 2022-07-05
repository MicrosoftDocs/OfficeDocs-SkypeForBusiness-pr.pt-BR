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
- seo-marvel-apr2020
description: Saiba mais sobre como atribuir licenças gratuitas da Conta de Recurso de Telefone do Teams ou licenças Telefonia do Teams Padrão usuário pagas a contas de recursos em sua organização.
ms.openlocfilehash: 07b47b2ec5b24b1edbfb599dc5a61e96169a02a2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615397"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>licenças Telefonia do Microsoft Teams conta de recurso do Telefonia do Microsoft Teams

As organizações com Telefonia do Teams Padrão ou Telefone do Teams com usuários licenciados do Plano de Chamada podem  atribuir uma licença gratuita da conta de recurso Telefonia do Microsoft Teams ou  uma licença de usuário Telefonia do Teams Padrão paga às contas de recursos. Um plano de chamada da Microsoft nem sempre é necessário (consulte Plan [for Teams Auto attendant and call queues](../plan-auto-attendant-call-queue.md#prerequisites) for prerequisites when transfering calls to an external phone number).

Todos os atendedores automáticos e filas de chamadas exigem uma conta de recurso associada. As contas de recurso que exigem um número de telefone  precisam de uma licença de conta de recurso Telefonia do Microsoft Teams gratuita  ou uma licença de usuário Telefonia do Teams Padrão paga antes que um número de telefone possa ser aplicado à conta de recurso.

> [!TIP]
> Nenhuma licença é necessária para contas de recursos que serão usadas com atendedores automáticos aninhados ou filas de chamadas que não têm um número de telefone atribuído. Consulte o diagrama a seguir para referência.

## <a name="resource-account-license-allocation"></a>Alocação de licença da Conta de Recurso

Sua organização é alocada Telefonia do Microsoft Teams *licenças* da Conta de Recurso, dependendo do tamanho geral. Qualquer organização que tenha pelo menos uma licença com recursos do Sistema de Telefonia do Teams, incluindo o Telefonia do Teams Padrão e o Telefone do Teams com licenças de Plano de Chamada, tem 25 licenças da Conta de Recurso disponíveis sem custo. Quando você adiciona 10 Telefonia do Teams Padrão ou Telefone do Teams com licenças de usuário do Plano de Chamada em sua organização, mais uma  Telefonia do Microsoft Teams de conta de recurso fica disponível.

> [!NOTE]
> Telefonia do Teams Padrão telefone do Teams com Plano de Chamada são licenças de complemento disponíveis para todos os assinantes do Microsoft 365. Telefonia do Teams Padrão licenças também são incluídas como parte dos planos Microsoft 365 E5 dados.

Se sua organização usa as licenças gratuitas Telefonia do Microsoft Teams *Conta* de Recurso na criação de nós de fila de chamadas ou atendedor automático, você ainda poderá usar as  licenças de Telefonia do Teams Padrão pagas com uma conta de recurso. A maioria das organizações terá licenças suficientes da Conta de Recurso com base no plano de dimensionamento.

### <a name="license-allocation-example"></a>Exemplo de alocação de licença

A Contoso, Inc. comprou 600 licenças que incluem o Sistema de Telefonia (uma para cada funcionário). A Contoso tem uma alocação inicial de 25 mais 60 *licenças Telefonia do Microsoft Teams conta* de recurso, 85 no total. Sua organização tem 90 filas de chamadas e atendedores automáticos que têm números de telefone. Eles precisam atribuir todas as licenças *Telefonia do Microsoft Teams conta* de recurso e obter cinco licenças de *Telefonia do Teams Padrão regulares*.

A Contoso deve considerar a reformulação do atendedor automático e do sistema de fila de chamadas. Se eles usarem menos números de telefone e mais nós aninhados que não precisam de um número de telefone, eles simplificarão a implementação e reduzirão os custos.

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>Como comprar licenças Telefonia do Microsoft Teams conta de recurso

1. Acesse o Centro de administração do Microsoft 365.
2. Vá para **Complementos de** >  Serviços  > **de Compra****de Cobrança**.
3. Role para encontrar a licença **Telefonia do Microsoft Teams Conta de** Recurso. Selecione **Comprar agora**.

   > [!NOTE]
   > Tenha em mente que você ainda deve **comprar** a licença, embora ela tenha um custo zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Alterar uma conta de recurso existente para usar uma licença Telefonia do Microsoft Teams conta de recurso

Se você decidir alternar a licença em sua conta de recurso de uma licença *Telefonia do Teams Padrão* para uma *licença Telefonia do Microsoft Teams conta de* recurso:

1. Obtenha a nova *licença Telefonia do Microsoft Teams conta de* recurso.
2. Siga as etapas vinculadas no Centro de administração do Microsoft 365 mover [usuários para uma assinatura diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Sempre remova uma licença *completa Telefonia do Teams Padrão* e atribua a licença *Telefonia do Microsoft Teams conta de* recurso na mesma atividade de licença. Se você remover a licença antiga, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta de recurso poderá não funcionar mais conforme o esperado. Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença *Telefonia do Microsoft Teams conta* de recurso e remova a conta de recurso interrompida.

## <a name="related-information"></a>Informações relacionadas

[Atualização do serviço Atendedor Automático e Filas de Chamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gerenciar contas de recursos no Microsoft Teams](../manage-resource-accounts.md)
