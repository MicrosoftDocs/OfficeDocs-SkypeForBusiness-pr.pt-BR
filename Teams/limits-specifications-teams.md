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
localization_priority: Priority
ms.collection:
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd9cdcd7abe3e86e540548bb735b89fa2c16bfe
ms.sourcegitcommit: 0de27096ea3c9d6f210aeb4aad31c4255c3c0244
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2019
ms.locfileid: "37615978"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limites e especificações para o Microsoft Teams

Este artigo descreve alguns dos limites, das especificações e de outros requisitos que se aplicam ao Teams.

## <a name="teams-and-channels"></a>Equipes e canais

|Recurso    | Limite máximo |
|-----------|---------------|
|Números de equipes que um usuário pode criar | Sujeito a um limite de objeto de 250&sup1;         |
|Número de equipes das quais um usuário pode ser membro|1.000|
|Número de membros em uma equipe | 5.000       |
|Número de equipes de toda a organização permitidas em um locatário | 5     |
|Número de membros em uma [equipe de toda a organização](create-an-org-wide-team.md) | 5.000       |
|Número de equipes que um administrador global pode criar        |  500.000   |
|Número de equipes que um locatário de Office 365 pode ter    | 500.000&sup2;     |
|Número de canais por equipe    | 200 (inclui canais excluídos)&sup3;         |

&sup1;Qualquer objeto de diretório no Azure Active Directory conta para este limite. Os administradores globais estão isentos desse limite, assim como os aplicativos que chamam o Microsoft Graph usando as [permissões de aplicativo](https://docs.microsoft.com/graph/permissions-reference).

&sup2;Esse limite inclui equipes arquivadas.

&sup3;Os canais excluídos podem ser restaurados dentro de 30 dias. Durante esses 30 dias, um canal excluído continua a ser contado no limite de 200 canais por equipe. Depois de 30 dias, um canal e seu conteúdo excluídos serão permanentemente excluídos e o canal deixará de contar com o limite de 200 canais por equipe.

## <a name="messaging"></a>Mensagens

### <a name="chat"></a>Chat

Os usuários que participam de conversas que fazem parte da lista de bate-papo do Teams precisam ter uma caixa de correio no Exchange Online (baseada em nuvem) para um administrador pesquisar as conversas de bate-papo. Isso ocorre porque as conversas que fazem parte da lista de bate-papo ficam armazenadas nas caixas de correio baseadas em nuvem dos participantes do bate-papo. Se um participante de bate-papo não tiver uma caixa de correio do Exchange Online, o administrador não poderá pesquisar nem fazer uma retenção das conversas de bate-papo. Por exemplo, em uma implantação híbrida do Exchange, os usuários com caixas de correio locais podem participar de conversas que fazem parte da lista de bate-papo do Teams. No entanto, nesse caso, o conteúdo dessas conversas não é pesquisável e não pode ser colocado em espera porque os usuários não têm caixas de correio baseadas em nuvem. (Para saber mais, confira [Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md).)

O bate-papo do Teams funciona em um back-end do Microsoft Exchange, para que os limites de mensagens do Exchange sejam aplicados à função de bate-papo dentro do Teams.

|Recurso  | Limite máximo  |
|---------|---------|
|Número de pessoas em um bate-papo particular <sup>1</sup>  | 100    |
|Número de anexos de arquivo<sup>2</sup>  |10     |

<sup>1</sup>Se você tiver mais de 20 pessoas em um bate-papo, os seguintes recursos de bate-papo serão desabilitados: respostas automáticas do Outlook e mensagens de status do Teams; indicador de digitação; chamadas de áudio e vídeo; compartilhamento; confirmação de leitura.

<sup>2</sup>Se o número de anexos exceder esse limite, você verá uma mensagem de erro.

### <a name="emailing-a-channel"></a>Enviar um email para um canal

 Se os usuários quiserem enviar um email para um canal no Teams, eles devem usar o endereço de email do canal. Quando um email faz parte de um canal, qualquer pessoa pode respondê-lo para iniciar uma conversa. Aqui estão alguns dos limites aplicáveis de envio de email para um canal.

|Recurso  | Limite máximo  |
|---------|---------|
|Tamanho da mensagem <sup>1<sup> | 24 KB |
|Número de anexos de arquivo<sup>2</sup>  |20     |
|Tamanho de cada anexo de arquivo | Menor que 10 MB |
|Número de imagens embutidas<sup>2</sup> |50   |

<sup>1</sup>Se a mensagem exceder esse limite, uma mensagem de visualização será gerada e o usuário será solicitado a baixar e exibir o email original no link fornecido.

<sup>2</sup>Se o número de anexos ou imagens exceder esse limite, você verá uma mensagem de erro.

Para obter mais informações, confira [Limites do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> O tamanho da mensagem, os anexos de arquivos e os limites de imagens embutidas são os mesmos em todas as licenças do Office 365.

## <a name="channel-names"></a>Nomes de canal

Os nomes de canal não podem conter os seguintes caracteres ou palavras.

|||
|---------|---------|
|Caracteres     | ~ # % & * { } + / \ : < > ? &#124; ' " ..        |
|Caracteres nesses intervalos    | 0 a 1F<br>80 a 9F        |
|Palavras     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 a COM9, LPT1 a LPT9, desktop.ini,  &#95;vti&#95;|

Os nomes de canal também não podem começar com um caractere de sublinhado (_), ponto final (.) ou terminar com um ponto final (.).

## <a name="meetings-and-calls"></a>Reuniões e chamadas

|Recurso     | Limite máximo |
|------------|---------------|
|Número de pessoas em uma reunião  | 250    |
|Tamanho máximo do arquivo do PowerPoint | 2GB|

## <a name="teams-live-events"></a>Eventos ao vivo do Teams

|Recurso     | Limite máximo |
|------------|---------------|
|Tamanho da audiência | 10.000 participantes |
|Duração do evento | 4 horas |
|Eventos ao vivo simultâneos em um locatário do office 365 | 15 |

Para saber mais sobre eventos ao vivo e uma comparação dos eventos ao vivo do Teams para a Transmissão de Reunião do Skype, vá para [Eventos ao vivo do Teams e Transmissão de Reunião do Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

## <a name="storage"></a>Armazenamento

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

Se o SharePoint Online não está habilitado em seu locatário, os usuários do Microsoft Teams nem sempre poderão compartilhar arquivos em equipes. Os usuários no bate-papo particular também não podem compartilhar arquivos, pois o OneDrive for Business (que é vinculado à licença do SharePoint) é necessário para essa funcionalidade.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas. (Para saber mais, confira [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).)

Como o Teams é executado em um back-end do SharePoint Online para compartilhamento de arquivos, as limitações do SharePoint se aplicam à seção Arquivos em uma Equipe. Estes são os limites de armazenamento aplicáveis ao SharePoint Online.

|Recurso                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Armazenamento                 |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização mais 10 GB por licença adquirida   |1 TB por organização mais 10 GB por licença adquirida |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização           |
|Armazenamento de arquivos do Teams |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |
|Limite de upload de arquivos (por arquivo)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Os canais são apoiados por pastas dentro do conjunto de sites do SharePoint Online criado para a equipe, para que as guias de arquivo dentro de Canais compartilhem os limites de armazenamento da equipe a que pertencem.

Para mais informações, confira [Limites do SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="contacts"></a>Contatos

O Teams usa estes contatos:

- Contatos no Active Directory da sua organização
- Contatos adicionados à pasta padrão do Outlook do usuário

Os usuários do Teams podem se comunicar com qualquer pessoa no Active Directory da sua organização e podem adicionar qualquer pessoa ao Active Directory da sua organização como um contato e às suas listas de contatos acessando **Bate-Papo** > **Contatos** ou **Chamadas** > **Contatos**.

Os usuários do Teams também podem adicionar uma pessoa que não esteja no Active Directory da sua organização como um contato, acessando **Chamadas** > **Contatos**.

## <a name="browsers"></a>Navegadores

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Sistemas operacionais

Para obter informações sobre os requisitos de sistema operacional, consulte [Obter clientes do Microsoft Teams](get-clients.md).
