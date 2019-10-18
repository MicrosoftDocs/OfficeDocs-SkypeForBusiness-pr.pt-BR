---
title: Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Saiba o que fazer quando precisar executar uma Descoberta Eletrônica, como quando precisar enviar todas as informações armazenadas eletronicamente para procedimentos judiciais.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42a9f9cc011d050e540eef3ff87d9cd839cc2819
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564028"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams
============================

Grandes empresas muitas vezes são expostas a grandes procedimentos legais de penalidade que exigem o envio de todas as ESI (informações armazenadas eletronicamente).

Todas as equipes 1:1 ou chats em grupo são registradas nas caixas de correio dos respectivos usuários e todas as mensagens de canal são registradas na caixa de correio do grupo que representa a equipe. Os arquivos carregados são cobertos pela funcionalidade de Descoberta Eletrônica para SharePoint Online e OneDrive for Business.

1.  Para conduzir uma investigação de descoberta eletrônica com o conteúdo do Microsoft Teams, examine [a](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) etapa 1 neste link.

2.  Os dados do Microsoft Teams serão exibidos como mensagens instantâneas ou conversas na saída de exportação do Excel para descoberta eletrônica, e você poderá montar o. PST no Outlook para exibir essas mensagens postar na exportação.

    Ao montar o .PST para a equipe, observe que todas as conversas serão mantidas na pasta Bate-papo em Equipe no Histórico de Conversas. O título da mensagem corresponde à Equipe a ao Canal. Ao analisar a imagem abaixo, você pode ver essa mensagem que Bob enviou ao canal Projeto 7 da equipe de Especificações de Fabricação.

    ![Captura de tela de uma pasta de chat de equipe na caixa de correio de um usuário no Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Para ver bate-papos privados na Caixa de Correio de um usuário, eles também estão localizados dentro da pasta Bate-papo em Equipe no Histórico de Conversas.

## <a name="ediscovery-of-guest-to-guest-chats"></a>Descoberta eletrônica de chats convidados para convidados

Sem uma caixa de correio, chats convidados para convidados (chats 1xN em que não há usuários locatários domésticos) não seriam indexados e, consequentemente, não seriam incluídos na descoberta eletrônica. Para facilitar a descoberta eletrônica para chats convidados a convidados, uma caixa de correio baseada em nuvem (ou uma caixa de correio fantasma) é criada para armazenar os dados do 1xN. Depois que os dados de chat de equipe são armazenados na caixa de correio baseada em nuvem, eles são indexados para pesquisa de conteúdo de descoberta eletrônica e conformidade.

A ilustração a seguir mostra como a descoberta eletrônica funciona para chats convidados a convidados em que não há uma caixa de correio.

![convidado para convidado-chats com e sem caixa de correio](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
