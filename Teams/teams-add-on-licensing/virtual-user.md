---
title: Microsoft Teams Telefone Padrão – Licenças de usuário virtual
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
description: Saiba mais sobre como atribuir licenças de usuário Teams Telefone Padrão – Usuário Virtual ou um usuário Teams Telefone licenças de usuário padrão para contas de recursos em sua organização.
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435725"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams Telefone Padrão – Licenças de usuário virtual

As organizações com Teams Telefone Standard ou Teams Telefone com usuários licenciados do Plano de Chamada podem atribuir uma licença de usuário *Microsoft Teams Telefone Standard – Virtual User* ou uma licença de usuário Teams Telefone *Standard paga*  licença de usuário para contas de recursos. Nem sempre é necessário um plano de chamada da Microsoft (consulte [Plan for Teams Auto attendant and call queues](../plan-auto-attendant-call-queue.md#prerequisites) for prerequisites when transfering calls to an external phone number).

Todos os atendimentos automáticos e filas de chamada exigem uma conta de recurso associada. As contas de recurso que exigem um número de telefone precisam de uma licença de usuário *Microsoft Teams Telefone Padrão – Usuário Virtual* ou  uma licença de usuário padrão Teams Telefone para que um número de telefone possa ser aplicado à conta de recurso.

> [!TIP]
> Nenhuma licença é necessária para contas de recursos que serão usadas com atendentes automáticos aninhados ou filas de chamadas que não tenham um número de telefone atribuído. Consulte o diagrama a seguir para fazer referência.

:::image type="content" alt-text="Licenças de usuário virtual." source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>Alocação de licença de usuário virtual

Sua organização é alocada Microsoft Teams Telefone *Standard –* Licenças de usuário virtual, dependendo de seu tamanho geral. Qualquer organização que tenha pelo menos uma licença com Teams Sistema de Telefonia, incluindo Teams Telefone Standard e Teams Telefone com licenças de Plano de Chamada, tem 25 licenças de Usuário Virtual disponíveis sem custo. Quando você adiciona 10 Teams Telefone Standard ou Teams Telefone com licenças de usuário do Plano de Chamada em sua organização Microsoft Teams Telefone, mais uma licença Padrão *– Usuário Virtual* fica disponível.

> [!NOTE]
> Teams Telefone Standard e Teams Telefone com Plano de Chamada são licenças de complemento disponíveis para todos os Microsoft 365 assinantes. Teams Telefone Licenças padrão também são incluídas como parte de Microsoft 365 E5 planos.

Se a sua organização usa as licenças de usuário *Microsoft Teams Telefone Padrão – Virtual na* criação de nós de fila de atendimento automático ou fila de chamada, você ainda poderá usar as  licenças padrão Teams Telefone pagas com uma conta de recurso. A maioria das organizações terá licenças de Usuário Virtual suficientes com base no plano de dimensionamento.

### <a name="license-allocation-example"></a>Exemplo de alocação de licença

A Contoso, Inc. comprou 600 licenças que incluem Sistema de Telefonia (uma para cada funcionário). A Contoso é alocada 25 mais 6 Microsoft Teams Telefone 0 licenças *Padrão – Usuário Virtual*, 85 no total. Sua organização tem 90 filas de chamadas e atendimentos automáticos que têm números de telefone. Eles precisam atribuir todas as licenças *padrão Microsoft Teams Telefone De usuário virtual* e obter cinco licenças padrão de Teams Telefone *de* preço regular.

A Contoso deve considerar o redesenho do atendimento automático e do sistema de filas de chamada. Se eles usarem menos números de telefone e nós mais aninhados que não precisam de um número de telefone, eles simplificam a implementação e reduzem os custos.

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>Como comprar Microsoft Teams Telefone Standard – Licenças de usuário virtual

1. Acesse o Centro de administração do Microsoft 365.
2. Vá para **BillingPurchase** >  **servicesAdd-ons** > .
3. Role até o final para encontrar a **licença Microsoft Teams Telefone Standard – Virtual User**. Selecione **Comprar agora**.

   > [!NOTE]
   > Lembre-se de que você ainda deve **Comprar** a licença mesmo que ela tenha um custo zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>Alterar uma conta de recurso existente para usar uma licença Microsoft Teams Telefone Standard – Virtual User

Se você decidir alternar a licença em sua conta de recurso de uma licença *Teams Telefone Standard* para uma licença *padrão Microsoft Teams Telefone Padrão – Usuário Virtual*:

1. Obter a nova licença Microsoft Teams Telefone Standard – Virtual User.
2. Siga as etapas vinculadas no Administração Microsoft 365 para [Mover usuários para uma assinatura diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Sempre remova uma licença *Teams Telefone Standard* e atribua *a licença Microsoft Teams Telefone Padrão – Usuário Virtual* na mesma atividade de licença. Se você remover a licença antiga, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta de recurso poderá não funcionar mais conforme esperado. Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença *Microsoft Teams Telefone Padrão – Usuário Virtual* e remova a conta de recurso quebrada.

## <a name="related-information"></a>Informações relacionadas

[Atendedor Automático e Atualização do Serviço de Filas de Chamada](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gerenciar contas de recursos no Microsoft Teams](../manage-resource-accounts.md)
