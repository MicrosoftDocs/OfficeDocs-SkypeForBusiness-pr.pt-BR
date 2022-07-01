---
title: Visualização pública no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenha mais informações sobre a prévia pública no Microsoft Teams. Experimente novos recursos e forneça comentários.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 25e3819b4ac14e770e55829d00654659970246f0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564119"
---
# <a name="microsoft-teams-public-preview"></a>Visualização Pública do Microsoft Teams

> [!NOTE] 
> Os recursos incluídos na visualização podem não estar completos e podem sofrer alterações antes de serem disponibilizados na versão pública. Eles são fornecidos apenas para fins de avaliação e exploração. As versões prévias do recurso não têm suporte na Nuvem da Comunidade Governamental (GCC) do Office 365.

A Visualização Pública para Microsoft Teams fornece acesso antecipado a recursos não lançados no Teams. As visualizações permitem que você explore e teste os próximos recursos. Também agradecemos comentários sobre qualquer recurso em visualizações públicas. A visualização pública é habilitada por usuário da equipe, então você não precisa se preocupar em afetar toda a sua organização.

Para obter uma lista do que está disponível na visualização pública do Teams, visite [Notas técnicas da Visualização Pública do Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview), [Notas de Versão do para Recursos de Administração do Teams](/OfficeUpdates/teams-admin)e [Novidades do Teams](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).

## <a name="set-the-update-policy"></a>Definir a política de atualização

A visualização pública é habilitada por usuário, e a opção para ativar a visualização pública é controlada em uma política administrativa. As políticas de atualização são usadas para gerenciar o Teams e os usuários de visualização do Office que verão os recursos de pré-lançamento ou de pré-visualização no aplicativo do Teams. Você pode usar a política Global (padrão Org-wide) e personalizá-la, ou criar uma ou mais políticas personalizadas para seus usuários.

1. Entre no [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).

2. Selecione **Teams** > **Teams Atualizar políticas**.

1. Selecione **Adicionar** para criar uma nova política ou selecione uma política existente para abrir **Atualizar política**.

2. Nomeie a política de atualização, adicione uma descrição e selecione a configuração **Mostrar recursos de visualização**.

   -   **Seguir a Pré-visualização do Office** (padrão)
       - Essa nova opção padrão habilitará automaticamente os recursos de Visualização Pública do Teams para qualquer usuário inscrito no Canal Office Atual (Pré-visualização). 
       - Não há mais ações necessárias para o usuário final.
   -   **Habilitado**
       - Essa opção habilita a Visualização Pública do Teams independentemente de um usuário estar inscrito no Canal Atual do Office (Pré-visualização). 
       - O usuário final também deve optar pela visualização pública do Teams no aplicativo Teams.

   > [!NOTE]  
   > Para usuários existentes na Visualização Pública do Teams que NÃO estão no **Canal Atual (Pré-visualização)**, os administradores de TI precisam mudar do padrão **Seguir o Office Preview** para **Habilitado**.
 
   - **Não habilitado** 
     - Os recursos de Visualização Pública do Teams não estarão disponíveis para os usuários finais.

    ![mostra a caixa de diálogo de configurações de visualização.](media/public-preview-policy.png)  

Você também pode definir a política usando o cmdlet `Set-CsTeamsUpdateManagementPolicy` PowerShell com o parâmetro `-AllowPublicPreview`.

## <a name="enable-public-preview"></a>Habilitar visualização pública

Para habilitar a visualização pública em uma área de trabalho ou cliente Web, você precisa concluir as seguintes tarefas:

1. Selecione os três pontos à esquerda do seu perfil para exibir o menu Teams.
2. Selecione **Sobre** > **Visualização pública**.
3. Selecione **Alternar para Visualização pública**.

> [!NOTE]  
> Essa opção só está disponível quando **Exibir recursos de pré-visualização** está definido como **Habilitado**.

### <a name="public-preview-for-microsoft-teams-rooms-on-windows"></a>Visualização pública para Salas do Microsoft Teams no Windows

A visualização pública está desativada por padrão. Quando a visualização pública está ativada, os usuários finais têm acesso a recursos que estão em visualização pública em habilitadas Salas do Teams. Para ativar a visualização pública, adicione ```<EnablePublicPreview>True</EnablePublicPreview>``` ao arquivo de configuração XML.

É recomendável registrar de 5 a 10 dispositivos na versão prévia pública. 

Todos os recursos de visualização pública são anunciados em [Versão Prévia Pública do Microsoft Teams – Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)

## <a name="teams-now-follows-office-preview-users"></a>O Teams agora segue os usuários do Office Preview

O novo padrão de política global da **Seguir a Pré-visualização do Office** permitirá que os usuários estejam automaticamente no canal de Visualização Pública do Teams se estiverem no Canal Atual (Pré-visualização) para o Cliente do Office 365 no Windows e Mac.

Microsoft Office continuará a receber atualizações do Canal Atual (Pré-visualização) e o cliente do Teams receberá atualizações por meio do canal de Visualização Pública. Esta política NÃO alternará os canais do Office com base nos canais do Teams. 

**Como manter seus usuários de visualização existentes do Teams que NÃO estão usando o Canal Atual do Office (Pré-visualização)?**

Para usuários existentes que você tem permissão para aceitar ou recusar a Visualização Pública do Teams e deseja manter essa configuração em seu formato atual, você precisará mudar do novo padrão **Seguir o Office Preview** para **Habilitado** (Consulte [Definir a política de atualização](#set-the-update-policy))

**Como recusar essa configuração?**

Você pode desabilitar a configuração do Centro de Administração do Teams de **Seguir o Office Preview** para **Não Habilitado** (Consulte [Definir a política de atualização](#set-the-update-policy))

## <a name="related-topics"></a>Tópicos relacionados

[Pré-visualização do desenvolvedor público](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
