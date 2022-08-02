---
title: Adobe Acrobat como um visualizador de PDF padrão no Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Saiba como definir o Adobe Acrobat como um visualizador de PDF padrão para exibir e editar arquivos PDF no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 913081ee0efc87d66ed304f3de5e9f00b69232fa
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156739"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat como um visualizador de PDF padrão no Microsoft Teams

> [!NOTE]
> No momento, o Adobe Acrobat como uma experiência de PDF padrão no Microsoft Teams só está disponível em versão prévia pública. Para usar essa funcionalidade, os administradores devem [](public-preview-doc-updates.md#enable-public-preview) habilitar a visualização pública para seu locatário e garantir que os usuários finais alterem a versão do cliente do Teams para visualização pública.

Como administrador, você pode definir o Adobe Acrobat como o aplicativo padrão para exibir e editar arquivos PDF no Microsoft Teams. Os usuários finais podem exibir, pesquisar, comentar e anotar arquivos PDF sem uma assinatura do Adobe Acrobat ou uma ID do Adobe.

## <a name="set-up-adobe-acrobat-app"></a>Configurar o aplicativo Adobe Acrobat

Antes de configurar o aplicativo, certifique-se de permitir que os aplicativos sejam usados em seu locatário, que você tenha permitido especificamente o aplicativo Adobe Acrobat e que as políticas de permissão do aplicativo o permitam. Para configurar o Adobe Acrobat como o aplicativo padrão para arquivos PDF, siga estas etapas:

1. Entre no centro de administração do Teams e acesse o aplicativo **Gerenciar aplicativos** > **[do](https://admin.teams.microsoft.com/policies/manage-apps)** Teams.

1. Pesquise o aplicativo Adobe Acrobat e selecione-o.

1. Na guia **Permissões** , selecione **Examinar permissão**.

   :::image type="content" source="media/permission-policy.png" alt-text="Captura de tela da permissão do aplicativo no Centro de administração do Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Selecione **Aceitar**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Instalar o aplicativo Adobe Acrobat para todos os usuários

Para atribuir e disponibilizar o aplicativo Adobe Acrobat para todos os usuários, siga estas etapas:

1. No Centro de administração do Teams, acesse as políticas **de Configuração de Aplicativos** > [**do**](https://admin.teams.microsoft.com/policies/app-setup) Teams.

1. Na **guia Gerenciar políticas** , selecione **Global (padrão em toda** a organização) e, em seguida, **selecione Editar**.

   :::image type="content" source="media/setup-policies.png" alt-text="Captura de tela das políticas de configuração do aplicativo Adobe Acrobat no Centro de administração do Teams.":::

1. Em Aplicativos Instalados, selecione **Adicionar aplicativos**.

1. **Pesquise Adobe Acrobat**, **selecione Adicionar** ao lado do nome do aplicativo e, em seguida, **selecione Adicionar**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Captura de tela que mostra como adicionar o aplicativo Adobe Acrobat para todos os usuários." lightbox="media/add-adobe-acrobat-app.png":::

1. Selecione **Salvar**.

Depois de selecionar salvar, o Teams usa o aplicativo Adobe Acrobat como o manipulador de arquivos padrão para arquivos PDF.

Se você quiser permitir seletivamente o aplicativo Adobe Acrobat para algumas pessoas ou para um grupo, poderá atribuir uma política de permissão de [aplicativo personalizada](teams-app-permission-policies.md).

Conheça as seguintes informações sobre essa funcionalidade:

* Depois que a política é configurada, normalmente leva [algumas horas](teams-app-setup-policies.md) para que o aplicativo esteja disponível para os usuários.
* Depois que a política for configurada, o aplicativo instalado estará disponível para os usuários após algumas horas.
* A exibição de arquivos PDF fixados em canais como uma guia e a exibição de arquivos PDF no aplicativo Atribuições continua a ser alimentada pela experiência nativa do Teams.
* O Adobe Acrobat como um visualizador de PDF padrão no Teams só funciona em clientes da Web e da área de trabalho. Não há suporte para ele no cliente móvel.
* Os usuários precisam de um plano do Adobe Acrobat para usar as ferramentas premium, como Exportar PDF, Organizar Páginas, Combinar Arquivos, Compactar PDF e Proteger PDF.
* Para desinstalar o aplicativo, os usuários finais podem remover o aplicativo do cliente do Teams. Administração pode remover o aplicativo Adobe Acrobat usando a política de instalação.
* Se você bloquear o aplicativo Adobe Acrobat, remova-o da política de configuração. Ele garante que a experiência do usuário final seja revertida para o uso do visualizador de arquivo PDF nativo.
* No cliente da área de trabalho do Teams, se você enfrentar problemas ao entrar no aplicativo Adobe Acrobat, use o navegador Teams para entrar.
