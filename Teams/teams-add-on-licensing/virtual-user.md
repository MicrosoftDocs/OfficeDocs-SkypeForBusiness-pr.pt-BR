---
title: Sistema de Telefonia do Microsoft 365 – Licenças de usuário virtual
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
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Saiba como atribuir uma licença gratuita do Sistema de Telefonia–Usuário Virtual ou uma licença de usuário paga do Sistema de Telefonia a contas de recursos em sua organização.
ms.openlocfilehash: 8e5322ccf7e3e7ad05c499b3dbcfdac65d0dfedb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116919"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Phone System – Licença de usuário virtual

Organizações com usuários licenciados do Sistema de Telefonia podem atribuir uma licença gratuita do Sistema de Telefonia do Microsoft 365 – Usuário Virtual ou uma licença de usuário paga do Sistema de Telefonia a contas de recursos. Um Plano de Chamada não é necessário. Todos os atendimentos automáticos ou filas de chamada exigem uma conta de recurso associada. As contas de recurso que exigem um número de telefone precisam de uma licença gratuita do Sistema de Telefonia do Microsoft 365 – Licença de usuário virtual ou uma licença de usuário paga do Sistema de Telefonia antes que um número de telefone possa ser aplicado à conta de recurso.

> [!TIP]
> Nenhuma licença é necessária para contas de recursos que serão usadas com atendentes automáticos aninhados ou filas de chamadas que não tenham um número de telefone atribuído. Consulte o diagrama a seguir para fazer referência: 

![Licenças de usuário virtual](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Alocação de licença de usuário virtual

Sua organização está alocada no Sistema de Telefonia do Microsoft 365 – Licenças de Usuário Virtual, dependendo de seu tamanho geral. Qualquer organização que tenha pelo menos uma licença, incluindo o Sistema de Telefonia ou tiver o Sistema de Telefonia adicionado, tem 25 licenças de Usuário Virtual disponíveis sem custo. Quando você adiciona 10 licenças de usuário do Sistema de Telefonia em sua organização, mais uma licença do Sistema de Telefonia do Microsoft 365 – Licença de usuário virtual fica disponível.

> [!NOTE]
> Sistema de Telefonia é uma licença de complemento disponível com o Microsoft 365 e o Office 365 E1 e o E3. O Sistema de Telefonia também está incluído como parte das licenças do Microsoft 365 E5, do Office 365 E5 e do Microsoft 365 Business Voice.

Se sua organização usa o Sistema de Telefonia gratuito do Microsoft 365 disponível – licenças de usuário virtual na criação de nós de atendimento automático ou fila de chamadas, você ainda pode usar as licenças do sistema de Telefone pago com uma conta de recurso. A maioria das organizações terá licenças de Usuário Virtual suficientes com base no plano de dimensionamento. 

### <a name="license-allocation-example"></a>Exemplo de alocação de licença

A Contoso, Inc. comprou 600 licenças que incluíam o Sistema de Telefonia (uma para cada funcionário). A Contoso está alocada em um 25 inicial mais 60 Sistema de Telefonia do Microsoft 365 – Licenças de usuário virtual, 85 no total. Sua organização tem 90 filas de chamadas e atendimentos automáticos que têm números de telefone. Eles precisam atribuir todas as licenças do Sistema de Telefonia do Microsoft 365 – Usuário Virtual e obter cinco licenças do Sistema de Telefonia com preço regular.

A Contoso deve considerar o redesenho do atendimento automático e do sistema de filas de chamada. Se eles usarem menos números de telefone e nós mais aninhados que não precisam de um número de telefone, eles simplificam a implementação e reduzem os custos.

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Como comprar o Sistema de Telefonia do Microsoft 365 – Licenças de usuário virtual

1. Acesse o Centro de administração do Microsoft 365.
2. Vá para **Complementos de**  >  **serviços de Compra** de  >  **Cobrança**
3. Role até o final para encontrar a licença do Sistema de **Telefonia do Microsoft 365 – Usuário Virtual.** Selecione **Comprar agora**.

> [!NOTE]
> Lembre-se de que você ainda deve  **Comprar** a licença mesmo que ela tenha um custo zero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Alterar uma conta de recurso existente para usar um Sistema de Telefonia do Microsoft 365 – Licença de usuário virtual

Se você decidir alternar a licença em sua conta de recurso de uma licença do Sistema de Telefonia para um Sistema de Telefonia do Microsoft 365 – Licença de usuário virtual:

1. Obter a nova licença do Microsoft 365 Phone System – Virtual User.
2. Siga as etapas vinculadas no Centro de administração do Microsoft 365 para [Mover usuários para uma assinatura diferente.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Sempre remova uma Licença completa do Sistema de Telefonia e atribua a licença do Sistema de Telefonia do Microsoft 365 – Usuário Virtual na mesma atividade de licença. Se você remover a licença antiga, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta de recurso poderá não funcionar mais conforme esperado. Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença Sistema de Telefonia do Microsoft 365 – Usuário Virtual e remova a conta de recurso quebrada. 

## <a name="related-information"></a>Informações relacionadas

[Atendedor Automático e Atualização do Serviço de Filas de Chamada](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gerenciar contas de recursos no Microsoft Teams](../manage-resource-accounts.md)