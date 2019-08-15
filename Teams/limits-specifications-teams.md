---
title: Limites e especificações para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Saiba mais sobre os limites, as especificações e outros requisitos que se aplicam ao Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecd31a243da999704b7d466b3dc93dd66fb7ac25
ms.sourcegitcommit: 9053c0d5ddb6be3ce3da85dffcde3f45dbc0ab7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407877"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limites e especificações para o Microsoft Teams

Este artigo descreve alguns dos limites, as especificações e outros requisitos que se aplicam ao Teams.

## <a name="teams-and-channels"></a>Equipes e canais 

|Recurso    | Limite máximo |
|-----------|---------------|
|Número de equipes que um usuário pode criar | Sujeito a um limite de objeto do 250&SUP1;         |
|Número de membros em uma equipe | 5.000       |
|Número de equipes de toda a organização permitidas em um locatário | 5     |
|Número de membros em uma [equipe de toda a organização](create-an-org-wide-team.md) | 5.000       |
|Número de equipes que um administrador global pode criar        |  500.000   |
|Número de equipes que um locatário do Office 365 pode ter    | 500.000&sup2;     |
|Número de canais por equipe    | 200 (inclui canais excluídos) &sup3;         |

&SUP1; Qualquer objeto de diretório no Azure Active Directory conta em direção a esse limite. Os administradores globais são isentos desse limite, assim como os aplicativos que chamam o Microsoft Graph usando [permissões de aplicativo](https://docs.microsoft.com/graph/permissions-reference).

&sup2; Esse limite inclui equipes arquivadas.

&sup3; os canais excluídos podem ser restaurados dentro de 30 dias. Durante esses 30 dias, um canal excluído continua a ser contado em direção ao canal de 200 por limite da equipe. Após 30 dias, um canal excluído e seu conteúdo são excluídos permanentemente, e o canal não conta mais em relação ao 200 canais por equipe.

## <a name="channel-names"></a>Nomes de canais

Os nomes de canais não podem conter os seguintes caracteres ou palavras.

|||
|---------|---------|
|Caracteres     | ~ #% & * {} +/\:  < > ? &#124; ""..        |
|Caracteres nestes intervalos    | 0 a 1F<br>80 a 9F        |
|Seja     | Forms, CON, CONIN $, CONOUT $, PRN, AUX, NUL, COM1 a COM9, LPT1 a LPT9, desktop. ini, &#95;VTI&#95;|

Os nomes de canal também não podem começar com um sublinhado (_) ou ponto (.) ou terminar com um ponto (.).

## <a name="meetings-and-calls"></a>Reuniões e chamadas

|Recurso     | Limite máximo |
|------------|---------------|
|Número de pessoas em uma reunião  | 250    |

## <a name="teams-live-events"></a>Eventos ao vivo do teams

|Recurso     | Limite máximo |
|------------|---------------|
|Tamanho da audiência | participantes do 10.000 |
|Duração do evento | 4 horas |
|Coluna1  |Column2  |
|---------|---------|
|Row1     |         |
|Row2     |         |

| Eventos dinâmicos simultâneos em um locatário do Office 365 | 15 |

Para obter mais informações sobre eventos dinâmicos e uma comparação de eventos ao vivo do teams para a transmissão de reunião do Skype, vá para [Teams Live eventos e transmissão de reunião do Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

## <a name="storage"></a>SPS

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

Se você não tiver o SharePoint Online habilitado no seu locatário, os usuários do Microsoft Teams nem sempre poderão compartilhar arquivos no Microsoft Teams. Os usuários no chat privado também não podem compartilhar arquivos porque o OneDrive for Business (que está vinculado à licença do SharePoint) é necessário para essa funcionalidade.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas. (Para saber mais, veja [como o SharePoint Online e o onedrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).)

Como as equipes são executadas em um back-end do SharePoint Online para compartilhamento de arquivos, as limitações do SharePoint se aplicam à seção arquivos de uma equipe. Estes são os limites de armazenamento aplicáveis para o SharePoint Online.

|Recurso                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|SPS                 |1 TB por organização, mais 10 GB por licença adquirida  |1 TB por organização, mais 10 GB por licença adquirida  |1 TB por organização, mais 10 GB por licença adquirida   |1 TB por organização, mais 10 GB por licença adquirida |1 TB por organização, mais 10 GB por licença adquirida  |1 TB por organização           |
|Armazenamento de arquivos do teams |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |
|Limite de carregamento de arquivos (por arquivo)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Os canais são apoiados por pastas dentro do conjunto de sites do SharePoint Online criado para a equipe, portanto, as guias de arquivo em canais compartilham os limites de armazenamento da equipe a que pertencem.

Para obter mais informações, consulte [limites do SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="messaging"></a>Mensagens

Os usuários que participam de conversas que fazem parte da lista de chat no Microsoft Teams devem ter uma caixa de correio do Exchange Online (baseada em nuvem) para que um administrador pesquise conversas de chat. Isso ocorre porque as conversas que fazem parte da lista de bate-papo ficam armazenadas nas caixas de correio baseadas em nuvem dos participantes do bate-papo. Se um participante de bate-papo não tiver uma caixa de correio do Exchange Online, o administrador não poderá pesquisar nem fazer uma retenção das conversas de bate-papo. Por exemplo, em uma implantação híbrida do Exchange, os usuários com caixas de correio locais podem participar de conversas que fazem parte da lista de bate-papo do Microsoft Teams. Entretanto, nesse caso, o conteúdo dessas conversas não pode ser pesquisada e não pode ser colocada em retenção porque os usuários não possuem caixas de correio baseadas em nuvem. (Para obter mais informações, consulte [como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md).)

A função de chat do Microsoft Teams funciona em um back-end do Microsoft Exchange, para que você possa aplicar os limites de mensagens do Exchange à função de chat no Microsoft Teams. Se os usuários quiserem enviar um email para um canal no Teams, eles usarão o endereço de email do canal. Quando um email faz parte de um canal, qualquer pessoa pode responder a ele para iniciar uma conversa. Aqui estão alguns dos limites aplicáveis para enviar emails para um canal. 

|Recurso  | Limite máximo  |
|---------|---------|
|Número de pessoas em um chat privado  | 100    |
|Tamanho da mensagem&dagger;  |25 KB   |
|Número de anexos de arquivo&Dagger;  |254     |
|Número de imagens embutidas&Dagger; |50   |

&dagger;Se a mensagem exceder esse limite, uma mensagem de visualização será gerada e o usuário será solicitado a exibir/baixar o email original do link fornecido.

&Dagger;Se o número de anexos ou imagens exceder esse limite, a mensagem não será processada e um email de NDR será enviado de volta para o remetente notificando sobre o erro.

> [!NOTE]
> Os limites tamanho da mensagem, anexos de arquivo e imagens embutidas são iguais em todas as licenças do Office 365.

Para obter mais informações, consulte [limites do Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="browsers"></a>Navegador

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Sistemas operacionais

Para obter informações sobre os requisitos do sistema operacional, consulte [obter clientes para o Microsoft Teams](get-clients.md).
