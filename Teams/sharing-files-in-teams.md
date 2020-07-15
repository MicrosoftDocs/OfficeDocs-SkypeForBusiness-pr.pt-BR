---
title: Compartilhando arquivos no Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Saiba mais sobre a experiência de compartilhamento de arquivos no Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138318"
---
# <a name="sharing-files-in-microsoft-teams"></a>Compartilhando arquivos no Microsoft Teams

No Microsoft Teams, os usuários podem compartilhar conteúdo com outros usuários de equipes dentro e fora de sua organização. O compartilhamento no Teams é baseado nas configurações definidas no SharePoint e no OneDrive, portanto, o que você configurou para o SharePoint e o OneDrive também controlará o compartilhamento no Teams.

## <a name="overview"></a>Visão geral

Os usuários podem compartilhar arquivos do OneDrive, de equipes e sites aos quais eles têm acesso e do computador. Para compartilhar um arquivo, os usuários podem fazer o seguinte:

- Em um canal, clique em **anexar** (o ícone de clipe de clipes), selecione **recente**, **navegue em equipes e canais**, **onedrive**ou **carregar de meu computador**e, em seguida, escolha o arquivo que deseja compartilhar. <br> 
    ![Captura de tela mostrando o compartilhamento de um arquivo de um canal](media/share-files-channel.png)
- Em um chat, clique em **anexar** (o ícone de clipe de clipe), selecione ou **onedrive** ou **carregar de meu computador**e, em seguida, escolha o arquivo que deseja compartilhar. <br>
    ![Captura de tela mostrando o compartilhamento de um arquivo de um chat](media/share-files-chat.png)
- Copie e cole o link de compartilhamento na caixa de texto.<br>
    ![Captura de tela mostrando a visualização de arquivo na caixa de texto](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>O que você precisa saber sobre a experiência de compartilhamento de arquivos

### <a name="permissions-of-shared-files-and-sharing-links"></a>Permissões de arquivos compartilhados e links de compartilhamento

Quando os usuários compartilham um arquivo navegando para ele no OneDrive ou em equipes e canais, todos os destinatários recebem acesso juntamente com a [permissão padrão definida no nível da organização](https://docs.microsoft.com/sharepoint/change-default-sharing-link).

Quando um usuário copia e cola um link de compartilhamento, as permissões definidas nesse link de compartilhamento são respeitadas e a URL do SharePoint é reduzida ao nome do arquivo. Em outras palavras, o Teams usa apenas o nome do arquivo para vincular a um arquivo.

Quando os usuários compartilham um arquivo no Teams, eles podem definir quem pode acessar o arquivo da mesma forma como fazem no Microsoft 365. Elas podem dar acesso a qualquer pessoa, às pessoas da sua organização, às pessoas com acesso existente ou a pessoas específicas (que podem incluir pessoas em um chat do 1:1, em um chat em grupo ou em um canal).  Quando um arquivo é compartilhado, a visualização do arquivo está disponível na mensagem, juntamente com todas as ações de arquivo, como **abrir online**, **baixar**e **Copiar link**. Por padrão, o arquivo é aberto no Teams. Às vezes, o link de compartilhamento pode não ter sido convertido em uma visualização de arquivo quando um usuário envia a mensagem. A visualização do arquivo será gerada pelo sistema, mas nesse cenário, o link de compartilhamento não será reduzido apenas para o nome do arquivo.

Quando os usuários compartilham um arquivo em um chat ou canal, eles são notificados se alguns ou todos os destinatários não têm permissão para exibir o arquivo. Eles podem alterar as permissões no arquivo antes de compartilhá-lo clicando na seta ao lado da visualização do arquivo que agora aparece na mensagem.

![Captura de tela da notificação se os destinatários não tiverem permissões](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Copiar um link de compartilhamento no Microsoft Teams

Os usuários podem copiar um link de compartilhamento do SharePoint e alterar as permissões de compartilhamento da mesma forma que no Microsoft 365. Elas podem dar acesso a qualquer pessoa, às pessoas de sua organização, às pessoas com acesso existente ou a pessoas específicas. A permissão padrão do link é a mesma do conjunto de permissões padrão no nível da organização, a menos que as permissões em nível de site do SharePoint o substituam.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>Configurar o compartilhamento no OneDrive e no SharePoint

Para obter mais informações sobre o compartilhamento de arquivos no OneDrive e no SharePoint, incluindo como configurar o compartilhamento e como ativar e desativar o compartilhamento, consulte:

- [Visão geral do compartilhamento externo](https://docs.microsoft.com/sharepoint/external-sharing-overview) – descreve o que acontece quando os usuários compartilham, dependendo do que estão compartilhando e com quem.

- [Gerenciar configurações de compartilhamento](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) – descreve como os administradores globais e do SharePoint podem alterar as configurações de compartilhamento no nível da organização para o SharePoint e o onedrive.

- [Ative ou desative o compartilhamento externo de um site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – descreve como os administradores globais e do SharePoint podem ativar ou desativar o compartilhamento externo de um site.

- [Altere o tipo de link padrão para um site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) – descreve como definir o tipo de link padrão para que seja mais restritivo.

## <a name="more-information"></a>Mais informações

- [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md)

- [SharePoint e Teams: melhor juntos](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [Compartilhar arquivos e pastas do OneDrive](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [Compartilhar arquivos ou pastas do SharePoint](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
