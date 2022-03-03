---
title: Configurar uma conta Microsoft Teams Sistema de Telefonia recurso
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Saiba como configurar uma conta de recurso Microsoft Teams Sistema de Telefonia para uso com os atendentes automáticos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0953ef81ef3128da858733931a43238531e83b6
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053240"
---
# <a name="step-4-set-up-a-teams-phone-system-resource-account"></a>Etapa 4: Configurar uma conta Teams Sistema de Telefonia de recursos

As contas de recursos não são atribuídas a nenhum usuário específico. Em vez disso, as contas de recurso, que usam uma licença de usuário virtual gratuita, são usadas por dispositivos e serviços em Microsoft 365. Em Microsoft Teams, as contas de recursos são atribuídas a números de telefone e são associadas a atendimentos automáticos e filas de chamadas.

Ao associar contas de recursos a atendimentos automáticos e filas de chamadas, você pode adicionar um ou mais números de telefone gratuitos ou de chamada gratuita a eles. Por exemplo, você pode associar uma conta de recurso a um número de chamada a um atendimento automático para chamadores locais. Para chamadas de longa distância, você pode associar outra conta de recurso a um número de chamada gratuita ao mesmo atendimento automático.

As seções deste artigo mostram como configurar uma conta de recurso e atribuir um número de telefone a ela. Mais tarde, você associará a conta de recurso a um atendente automático.

## <a name="obtain-virtual-user-licenses"></a>Obter licenças de usuário virtual

As contas de recursos exigem uma licença para trabalhar com os atendimentos automáticos e filas de chamada. Você pode usar uma licença *de usuário Microsoft Teams Telefone Standard - Virtual* User.

> [!NOTE]
> Você só deverá executar as etapas a seguir se tiver se inscreveu para um Teams Telefone período de avaliação de licença do pacote de planos de chamada. Se você comprou Teams Telefone licenças de pacote do Plano de Chamada, as licenças virtuais já devem ser aplicadas à sua conta.
>
> Para ver se você já tem licenças virtuais, entre Microsoft 365 usando uma conta com permissões de administrador global. Em seguida, vá para Cobrança > [Seus produtos](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Se você tiver licenças virtuais, elas aparecerão como **Microsoft Teams Telefone Padrão - Usuário Virtual**.

1. Abra o Centro de administração do Microsoft 365 e faça logoff com um usuário que seja um administrador global. Geralmente, essa é a conta que você usou para se inscrever no Microsoft 365.
2. No painel de navegação esquerdo, vá até <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**BillingPurchase** > </a> **servicesAdd-onsSee** >  >  **todos os produtos Complementos**.
3. Role até o final para encontrar a **licença Microsoft Teams Telefone Standard – Virtual User**. Selecione **Detalhes** e **, em seguida, Comprar**.
4. Na página de compra de licença, selecione o número de licenças de usuário virtual que você deseja. Você precisa de uma licença virtual para cada atendimento automático e fila de chamada que planeja configurar. Recomendamos selecionar pelo menos cinco licenças para que você possa facilmente configurar mais atendimentos automáticos e filas de chamada no futuro sem precisar comprar mais licenças imediatamente.
5. **Desmarque Atribuir automaticamente a todos os seus usuários sem licenças**.
6. Selecione **Check-out agora**.
7. Confirme seu pedido, selecione **Próximo** e, em seguida **, Coloque a ordem**.

> [!NOTE]
> Lembre-se de que você ainda deve  **Comprar** a licença mesmo que ela tenha um custo zero.

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

Depois de receber sua licença *Padrão Microsoft Teams Telefone Usuário Virtual*, você poderá criar sua conta de recurso.

1. Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global. Geralmente, essa é a conta que você usou para se inscrever no Microsoft 365.
2. No painel de navegação esquerdo, acesse <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Configurações em toda a** >  **organizaçãoResource contas**</a>.
3. Selecione **Adicionar**.
4. No painel **Adicionar conta de** recurso, preencha **Nome de exibição** e, em seguida, **Nome de usuário**. Escolha um nome de exibição descritivo, como "Atendimento automático de linha principal" para descrever a finalidade da conta de recurso.
5. Em **Tipo de conta de recurso**, selecione **Atendimento automático**.
6. Selecione **Salvar**.

## <a name="assign-a-license"></a>Atribuir uma licença

Depois de criar sua conta de recurso, você precisará atribuir uma licença *Microsoft Teams Telefone Standard - Virtual User* ou *Teams Telefone Standard.*

1. Abra o Centro de administração do Microsoft 365 e faça logoff com um usuário que seja um administrador global. Geralmente, essa é a conta que você usou para se inscrever no Microsoft 365.
1. No painel de navegação esquerdo, vá para <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**UsuáriosActive** >  usuários</a>.
1. Selecione sua conta de recurso.
1. Na guia **Licenças e Aplicativos**, em **Licenças**, selecione **Microsoft Teams Telefone Padrão - Usuário Virtual**.
1. Selecione **Salvar alterações** e **, em seguida, Fechar**.

## <a name="assign-a-service-number"></a>Atribuir um número de serviço

1. Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global. Geralmente, essa é a conta que você usou para se inscrever no Microsoft 365.
1. No painel de navegação esquerdo, acesse <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Configurações em toda a** >  **organizaçãoResource contas**</a>.
1. Selecione a conta de recurso que você acabou de criar e clique em **Atribuir/desatribuição**.
1. Na lista **Telefone de tipos de número**, escolha **Online**.
1. Na caixa **Número de telefone atribuído** , pesquise o número que deseja usar e clique em **Adicionar**. Certifique-se de incluir o código do país (por exemplo, **+1** 250 555 0012)
1. Clique em **Salvar**.

> [!div class="nextstepaction"]
> [Próxima etapa: Atribuir números de telefone aos usuários](set-up-assign-numbers.md)
