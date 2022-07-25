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
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002331"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Adobe Acrobat como um visualizador de PDF padrão no Teams

> [!NOTE]
> No momento, o Adobe Acrobat como uma experiência de PDF padrão no Teams só está disponível em versão prévia pública. [Habilite a visualização](public-preview-doc-updates.md#enable-public-preview) pública para seu locatário antes de usar esse recurso. Certifique-se de que os usuários finais alterem a versão do cliente do Teams para visualização pública para experimentar o Adobe Acrobat como visualizador de PDF no Teams.

Como administrador, você pode definir o Adobe Acrobat como o aplicativo padrão para exibir e editar arquivos PDF no Microsoft Teams. Os usuários finais não precisam de uma assinatura do Adobe Acrobat ou de uma ID do Adobe para exibir, pesquisar, comentar e anotar arquivos PDF.

## <a name="set-up-adobe-acrobat-app"></a>Configurar o aplicativo Adobe Acrobat

Para configurar o Adobe Acrobat como o aplicativo padrão para exibir arquivos PDF, siga estas etapas:

1. Entre no centro de administração do Teams e acesse o aplicativo **Gerenciar aplicativos** > **[do](https://admin.teams.microsoft.com/policies/manage-apps)** Teams.

1. Pesquise o aplicativo Adobe Acrobat e selecione **o aplicativo Adobe Acrobat** .

   > [!NOTE]
   >
   > * Verifique se o status do aplicativo Adobe Acrobat está definido como **Permitido**. Caso contrário, habilite **a alternância** Permitido.
   > * Se houver alguma configuração de administrador existente na política de permissão do aplicativo ou nas configurações de aplicativo em toda a organização que tenha bloqueado o aplicativo, certifique-se de permitir o aplicativo na política de permissão do aplicativo ou nas configurações do aplicativo em toda a [organização](teams-app-permission-policies.md).[](teams-app-permission-policies.md)

1. Na guia **Permissões** , selecione **Examinar permissão**.

1. Selecione **Aceitar**.

   :::image type="content" source="media/permission-policy.png" alt-text="Captura de tela da permissão do aplicativo no Centro de administração do Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>Instalar o aplicativo Adobe Acrobat para todos os usuários

Você pode usar a política Global (padrão em toda a organização) para atribuir e disponibilizar o aplicativo Adobe Acrobat para todos os usuários. Esta etapa dispara um sinal no Teams para definir o aplicativo como o manipulador de arquivos padrão para arquivos PDF. Para atribuir o aplicativo Adobe Acrobat para todos os usuários, siga estas etapas:

1. No Centro de administração do Teams, acesse as políticas **de Configuração de Aplicativos** > [**do**](https://admin.teams.microsoft.com/policies/app-setup) Teams.

1. Na **guia Gerenciar políticas** , selecione **Global (padrão em toda** a organização) e, em seguida, **selecione Editar**.

   :::image type="content" source="media/setup-policies.png" alt-text="Captura de tela das políticas de configuração do aplicativo Adobe Acrobat no Centro de administração do Teams.":::

1. Em Aplicativos Instalados, selecione **Adicionar aplicativos**.

1. **Pesquise Adobe Acrobat**, **selecione Adicionar** ao lado do nome do aplicativo e, em seguida, **selecione Adicionar**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Captura de tela que mostra como adicionar o aplicativo Adobe Acrobat para todos os usuários." lightbox="media/add-adobe-acrobat-app.png":::

1. Selecione **Salvar**.

Depois de selecionar salvar, o aplicativo Adobe Acrobat é configurado com o Teams para abrir todos os arquivos PDF no aplicativo Adobe Acrobat no aplicativo de chat, canal ou arquivos.

Se você quiser permitir seletivamente o aplicativo Adobe Acrobat para algumas pessoas específicas ou para um grupo, poderá atribuir uma política [de permissão de aplicativo personalizada](teams-app-permission-policies.md).

Conheça as seguintes informações sobre essa funcionalidade:

* Depois que a política é configurada, normalmente leva [algumas horas](teams-app-setup-policies.md) para que o aplicativo esteja disponível para os usuários.
Depois que a política for configurada, o aplicativo instalado estará disponível para os usuários após algumas horas.
* A exibição de arquivos PDF fixados em canais como uma guia e a exibição de arquivos PDF no aplicativo de atribuições continua a ser alimentada pela experiência nativa do Teams.
* O Adobe Acrobat como um visualizador de PDF padrão no Teams só funciona em clientes da Web e da área de trabalho. Não há suporte para ele no cliente móvel.
* Os usuários precisam de um plano do Adobe Acrobat para usar ferramentas premium, como Exportar PDF, Organizar Páginas, Combinar Arquivos, Compactar PDF e Proteger PDF.

> [!NOTE]
> No cliente da área de trabalho do Teams, se você enfrentar problemas ao entrar no aplicativo Adobe Acrobat, poderá abrir o Teams no navegador e entrar. Esse é um problema conhecido e será resolvido até setembro de 2022.

## <a name="faqs"></a>Faqs

* Como remover o aplicativo Adobe Acrobat do cliente do Teams?
  
  Os usuários finais podem desinstalar o aplicativo do cliente e o administrador do Teams pode remover o aplicativo Adobe Acrobat da política de configuração.

* Os administradores podem bloquear o aplicativo Adobe Acrobat depois que ele for definido como um manipulador padrão?
  
  Sim, mas antes que o administrador bloqueie o aplicativo, remova a política de configuração para garantir que os usuários finais sejam trazidos de volta com segurança para a experiência padrão do Teams.
