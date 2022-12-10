---
title: Adobe Acrobat como visualizador de PDF padrão no Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 09/25/2022
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Saiba como definir o Adobe Acrobat como visualizador de PDF padrão para exibir e editar arquivos PDF no Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 67be332ee916f30b0341dc3ac03e047558cead0c
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343272"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>Definir o Adobe Acrobat como o visualizador DE PDF padrão no Microsoft Teams

Como administrador, você pode definir o Adobe Acrobat como o aplicativo padrão para exibir e editar arquivos PDF no Microsoft Teams. Os usuários finais podem exibir e pesquisar os arquivos PDF. Os usuários também podem comentar e anotar os arquivos PDF gratuitamente depois de entrarem.

Para configurar o aplicativo Adobe Acrobat como o manipulador padrão para arquivos PDF em seu locatário, conclua as seguintes etapas como pré-requisitos:

* [Permita o aplicativo Adobe Acrobat](#allow-adobe-acrobat-app-in-your-tenant).
* [Instale o aplicativo Adobe Acrobat](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Permitir o aplicativo Adobe Acrobat em seu locatário

Para configurar o aplicativo como um visualizador DE PDF padrão, verifique se você permite que o [aplicativo de terceiros seja usado](manage-apps.md#manage-org-wide-app-settings) em seu locatário. Em seguida, siga as instruções a seguir para configurar o Adobe Acrobat como o aplicativo padrão para arquivos PDF.

1. Entre no centro de administração do Teams e acesse **o aplicativo** >  Teams **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Pesquise o aplicativo Adobe Acrobat e selecione-o. Ele abre a página de detalhes do aplicativo.

1. Selecione a guia **Permissões** e selecione **Examinar permissão**.

   :::image type="content" source="media/permission-policy.png" alt-text="Captura de tela da permissão do aplicativo no Centro de administração do Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Selecione **Aceitar**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Instalar o aplicativo Adobe Acrobat para todos os usuários

Para atribuir e disponibilizar o aplicativo Adobe Acrobat para todos os usuários, siga estas etapas:

1. No Centro de administração do Teams, acesse **Aplicativo Teams** > [**Políticas de configuração**](https://admin.teams.microsoft.com/policies/app-setup).

1. Na guia **Gerenciar políticas**, selecione **Global (padrão em toda a organização)** e, em seguida, selecione **Editar**.

   :::image type="content" source="media/setup-policies.png" alt-text="Captura de tela das políticas de configuração do aplicativo Adobe Acrobat no Centro de administração do Teams.":::

1. Em Aplicativos instalados, selecione **Adicionar aplicativos**.

1. Pesquise **Adobe Acrobat**, selecione **Adicionar** ao lado do nome do aplicativo e, em seguida, selecione **Adicionar**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Captura de tela que mostra como adicionar o aplicativo Adobe Acrobat para todos os usuários." lightbox="media/add-adobe-acrobat-app.png":::

1. Selecione **Salvar**.

1. Opcionalmente, você pode permitir o SSO com Microsoft Azure Active Directory identidade se tiver uma licença do Adobe Acrobat. Recomendamos configurar o SSO usando as instruções em [Configurar identidade e logon único](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

Depois de concluir a configuração, o Teams usa o aplicativo Adobe Acrobat como o manipulador de arquivos padrão para arquivos PDF.

Se você quiser permitir seletivamente o aplicativo Adobe Acrobat para alguns indivíduos ou para um grupo, use [políticas de permissão do aplicativo](teams-app-permission-policies.md).

## <a name="considerations-and-limitations"></a>Considerações e limitações

Conheça as seguintes informações sobre essa funcionalidade:

* Depois que a política é configurada, normalmente [leva algumas horas](teams-app-setup-policies.md#considerations-and-limitations) para o aplicativo estar disponível para os usuários.
* A experiência nativa em PDF do aplicativo Teams está disponível para exibir arquivos PDF que estão fixados em canais como uma guia e estão disponíveis no aplicativo Atribuições.
* O Adobe Acrobat como um visualizador de PDF padrão no Teams só funciona em clientes da Web e da área de trabalho. Não há suporte para ele no cliente de dispositivo móvel.
* Os usuários precisam de um plano do Adobe Acrobat para usar as ferramentas premium, como Exportar PDF, Organizar Páginas, Combinar Arquivos, Compactar PDF e Proteger PDF.
* Para desinstalar o aplicativo, os usuários finais podem remover o aplicativo do cliente do Teams. Administração pode remover o aplicativo Adobe Acrobat usando a política de configuração.
* Se você bloquear o aplicativo Adobe Acrobat, remova o aplicativo da política de configuração. Isso garante que a experiência do usuário final seja revertida para o uso do visualizador de arquivo PDF nativo.
* Se você enfrentar problemas para entrar no aplicativo Adobe Acrobat no cliente da área de trabalho do Teams, use o [navegador teams no](https://teams.microsoft.com/) para entrar.
* Entre em uma [conta gratuita da Adobe](https://acrobat.adobe.com/us/en/) para comentar ou anotar nos arquivos PDF. O aplicativo no Teams pode oferecer funcionalidades como anotar, organizar, compactar e proteger arquivos PDF. Para obter uma lista completa de funcionalidades e os pré-requisitos, consulte [Gerenciar arquivos PDF no aplicativo Teams with Acrobat](https://www.adobe.com/content/dam/dx-dc/pdf/ue/acrobat-msft-teams-feature-comp-ue.pdf).
* Quando você colabora em um documento PDF, ele é armazenado temporariamente (por até 24 horas) nos servidores do Adobe na região em que você está localizado. Esse armazenamento temporário é para facilitar o processamento transitório. Seus documentos são criptografados de ponta a ponta ao serem transferidos do sistema de arquivos local para o servidor e permanecem criptografados no servidor também. consulte [segurança para Acrobat](https://aka.ms/Adobe_Acrobat_Security).
