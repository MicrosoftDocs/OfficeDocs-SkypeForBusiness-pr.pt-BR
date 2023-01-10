---
title: Retirar Microsoft Teams Gratuito (clássico) para sua organização
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: alyake
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
robots: noindex
description: Saiba como remover as licenças gratuitas (clássicas) do Teams e atribuir licenças pagas do Teams para os usuários da sua organização.
ms.openlocfilehash: 027f84577a50d445eb01bce896417f23e503abb7
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749148"
---
# <a name="retire-microsoft-teams-free-classic-for-your-organization"></a>Retirar Microsoft Teams Gratuito (clássico) para sua organização

Em meados de abril de 2023, a Microsoft retirará a **licença de Microsoft Teams Gratuito (clássico)**.

Este artigo fornece instruções de administradores de TI sobre como retirar as licenças **de Microsoft Teams Gratuito (clássico)** de sua organização e migrar para licenças pagas do Teams.

Se você não mover as licenças gratuitas do Teams de seus usuários para licenças pagas do Teams até meados de abril de 2023, seus usuários perderão o acesso ao Teams.

Para concluir esse processo, você pode escolher um dos dois métodos:

- [Use o Centro de administração do Microsoft 365.](#use-microsoft-365-admin-center-to-replace-licenses)
- [Use Microsoft PowerShell.](#use-microsoft-powershell-to-replace-licenses)

Se sua organização decidir não migrar para uma licença paga do Teams, você poderá exportar o conteúdo da sua organização do Teams. Para obter instruções sobre como exportar conteúdo do Teams, consulte [Exportar conteúdo com APIs de exportação do Microsoft Teams](/microsoftteams/export-teams-content).

## <a name="use-microsoft-365-admin-center-to-replace-licenses"></a>Usar Centro de administração do Microsoft 365 para substituir licenças

Se sua organização tiver poucos usuários **atribuídos à licença do Teams Free (clássica),** recomendamos usar o Centro de administração do Microsoft 365 para remover e atribuir licenças.

### <a name="check-users-current-teams-licensing"></a>Verificar o licenciamento atual do Teams dos usuários

1. Entre no [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
1. No menu esquerdo, acesse **Usuários** > e selecione [**Usuários ativos**](https://go.microsoft.com/fwlink/p/?linkid=834822) para exibir licenças atribuídas aos usuários.
    1. A coluna **Licença** mostrará **Microsoft Teams Gratuito (clássico)** ao lado dos usuários atribuídos a essa licença.
1. No menu esquerdo, vá para **Cobrança** > e selecione [**Licenças**](https://go.microsoft.com/fwlink/p/?linkid=842264) para ver se você tem licenças pagas do Teams disponíveis.
    1. Se sua organização tiver licenças disponíveis, [pule para Atribuir licenças pagas do Teams](#assign-paid-teams-licenses) para atribuir essas licenças aos usuários com licenças **gratuitas do Teams (clássicas** ).
1. Determine o número de licenças pagas do Teams que você precisa comprar, se houver.

### <a name="purchase-paid-teams-licenses"></a>Comprar licenças pagas do Teams

1. No [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), acesse **> de Cobrança** e selecione **Comprar serviços**.
1. Selecione **Exibir produtos** para exibir todas as licenças disponíveis.
1. Selecione o filtro **de categoria comunicação e colaboração** para ver as licenças do Teams.
1. Escolha a licença paga do Teams que você gostaria de substituir **o Teams Free (clássico)**.
    1. Recomendamos a [licença **do Teams Essentials**](https://admin.microsoft.com/adminportal/home#/catalog/offer-details/microsoft-teams-essentials-aad-identity-/2D7C59AC-F814-43E0-8E8E-E4EA91A09CAF), que está disponível até 300 lugares.
    1. Se você precisar de mais de 300 assentos, recomendamos comprar [licenças do Microsoft 365 E1](https://admin.microsoft.com/Adminportal/Home#/catalog/offer-details/office-365-e1/CF4A479A-2119-4EF2-83D1-37CF8460EADA).
1. Insira o número de licenças que você gostaria de comprar e escolha uma frequência de cobrança.
1. Selecione o botão **Comprar** para concluir o processo de compra.

#### <a name="purchase-licenses-in-the-admin-center-marketplace"></a>Comprar licenças no Marketplace do centro de administração

Alguns locatários têm acesso ao Centro de administração do Microsoft 365 Marketplace. Para esses locatários, você comprará licenças no Marketplace.

1. No [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), selecione **Marketplace** no menu esquerdo.
1. Selecione a guia **Todos os produtos** .
1. Selecione o filtro **de categoria comunicação e colaboração** para ver as licenças do Teams.
1. Escolha a licença paga do Teams que você gostaria de substituir **o Teams Free (clássico)**.
1. Insira o número de licenças que você gostaria de comprar e escolha uma frequência de cobrança.
1. Selecione o botão **Comprar** para concluir o processo de compra.

### <a name="assign-paid-teams-licenses"></a>Atribuir licenças pagas do Teams

1. Quando estiver pronto para substituir as licenças **do Teams Free (clássico),** no Centro de administração do Microsoft 365, acesse **Usuários** > [**Ativos**](https://admin.microsoft.com/adminportal/home#/users).
1. Selecione todos os usuários com a licença **Do Teams Free (clássica)** listada na coluna **Licenças** .
1. Na parte superior do centro de administração, selecione a opção **Gerenciar licenças de produto** .
1. No painel do lado direito, selecione **Substituir**.
    1. Selecionar a opção **Substituir** exige que você reelege todas as licenças que deseja que esses usuários sejam atribuídos. Se você selecionar apenas a nova licença paga do Teams, as outras licenças atribuídas a esses usuários serão removidas dos usuários e substituídas pela licença do Teams.
    1. Se os usuários tiverem necessidades de licenciamento diferentes, conclua esse processo em lotes para impedir o licenciamento incorreto de usuários.
1. No painel do lado do passeio, escolha a nova licença paga do Teams e quaisquer outras licenças que os usuários devem ser atribuídas e selecione o botão **Salvar alterações** .

## <a name="use-microsoft-powershell-to-replace-licenses"></a>Usar o Microsoft PowerShell para substituir licenças

Se sua organização tiver um grande número de usuários atribuídos à licença **Do Teams Free (clássica),** recomendamos usar o PowerShell para desatribuir em massa e atribuir licenças aos usuários.

Antes de concluir esse processo, você precisará de licenças pagas do Teams para usuários atribuídos à licença **do Teams Free (clássica** ). Para comprar licenças para esses usuários, consulte [Comprar licenças pagas do Teams](#purchase-paid-teams-licenses).

1. Conecte seu locatário do Microsoft 365 ao [SDK do Microsoft Graph PowerShell](/powershell/microsoftgraph/get-started).
1. Abra o aplicativo de área de trabalho do Microsoft PowerShell.
1. [Defina permissões de usuário e organização para API do Graph](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#use-the-microsoft-graph-powershell-sdk).
1. [Remova licenças **gratuitas do Teams (clássicas)** de contas de usuários](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#removing-licenses-from-user-accounts).
1. [Atribua licenças pagas do Teams aos usuários](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell#assigning-licenses-to-user-accounts).

Para obter mais informações sobre o processo do SDK do Graph PowerShell, consulte [Usar o SDK do Microsoft Graph PowerShell](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell).
