---
title: Criar uma conta de recurso usando o centro de administração do Microsoft 365
description: Se preferir usar uma interface gráfica de usuário, você poderá criar uma conta de recurso para as salas e as barras de colaboração do Microsoft Teams do Microsoft Teams usando o centro de administração do Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: criar conta de dispositivo, interface do usuário do Microsoft 365, centro de administração do Microsoft 365
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268006"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Criar uma conta de recurso do Microsoft 365 usando o centro de administração do Microsoft 365

As contas de recursos do Microsoft 365 são contas de caixa de correio e de equipe dedicadas a recursos específicos, como uma sala, um projetor e assim por diante. Essas contas de recursos podem responder automaticamente aos convites de reunião usando regras definidas quando são criadas. Por exemplo, se você tiver um recurso comum, como uma sala de conferência, poderá configurar uma conta de recurso para essa sala de conferência que aceitará ou recusará automaticamente convites de reunião, dependendo da disponibilidade do calendário.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licenças

Antes de criar uma conta de recurso do Microsoft 365, verifique o tipo de licença necessário. Se você usar apenas uma conta do recurso para agendar um recurso (ou seja, convidar o recurso para a reunião e ele aceitar ou recusar o convite automaticamente), você não precisará atribuir uma licença a uma conta do recurso. Você precisará atribuir uma licença para a conta do recurso nas seguintes situações:

- **Reunião do teams** Se você quiser que o recurso (como um console de salas do Microsoft Teams, barra de colaboração e assim por diante) ingresse em uma reunião de equipe para que os participantes possam usá-lo para apresentar vídeo e áudio por meio dele, você precisará de uma licença de sala de reunião. 
- **Chamadas PSTN** Se quiser que o recurso faça ou receba chamadas para ou de um número de telefone externo (chamado de uma rede telefônica pública comutada ou chamada PSTN), você precisará de um sistema telefônico Microsoft 365 ou da licença de voz do Microsoft 365 Business.

Para obter mais informações sobre sala de reunião, sistema telefônico e licenças de voz para empresas, consulte [licenças de Complementos do Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Criar uma conta de recurso no centro de administração do Microsoft 365

1. Acesse o Microsoft 365 visitandohttps://admin.microsoft.com
2. Forneça as credenciais de administrador para o seu locatário do Microsoft 365. Isso o levará ao centro de administração do Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centro de administração do Microsoft 365":::
3. No centro de administração, navegue até **recursos** no painel esquerdo (talvez seja necessário selecionar **Mostrar todos os** primeiros) e, em seguida, selecione **salas & equipamento**.

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centro de administração do Microsoft 365-recursos":::
4. Selecione **Adicionar uma caixa de correio de recurso** para criar uma nova conta de sala. Digite um nome de exibição e um endereço de email para a conta, selecione **Adicionar**e **fechar**. Recomendamos que você padronize uma Convenção de nomenclatura para todas as suas contas de recursos.

> [!NOTE]
> Por padrão, as contas de recurso são definidas com as configurações a seguir. Se desejar alterá-los, selecione **definir opções de agendamento** antes de selecionar **fechar**. Se desejar alterá-los mais tarde, navegue até salas de **recursos**  >  **& equipamento**, selecione a conta do recurso e, em seguida, selecione **Editar** em **Opções de reserva**.
>
> - Permitir repetição de reuniões
> - Recusar reuniões automaticamente fora dos seguintes limites
>   - Janela de reserva (dias): 180
>   - Duração máxima (horas): 24
> - Aceitar solicitações de reunião automaticamente

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centro de administração do Microsoft 365 – adicionar recursos":::
5. Navegue até a seção **usuários** no centro de administração e, na lista **usuários ativos** , você verá a sala que acabou de criar.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centro de administração do Microsoft 365-ver usuários ativos":::
6. Selecione o nome da sala e um painel de propriedades da conta será exibido à direita.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centro de administração do Microsoft 365 – Propriedades do usuário":::
7. Agora, você precisa atribuir uma senha à conta do recurso. No painel, você pode ver as propriedades da conta e várias ações opcionais. Selecione o ícone redefinir chave da **senha** abaixo do nome de usuário para alterar a senha. Desmarque **exigir que este usuário altere a senha quando entrarem pela primeira vez**. Não é possível alterar a senha por meio do processo de entrada do dispositivo. Selecione **Redefinir**.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centro de administração do Microsoft 365-Redefinir senha":::
8. Na seção **licenças e aplicativos** , defina **selecionar local** para o país ou a região onde o dispositivo será instalado. Role a tela para baixo e marque a caixa ao lado da licença a ser atribuída, como sala de reunião, e escolha **salvar alterações**. A licença pode variar dependendo da sua organização.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centro de administração do Microsoft 365-atribuir licença":::
