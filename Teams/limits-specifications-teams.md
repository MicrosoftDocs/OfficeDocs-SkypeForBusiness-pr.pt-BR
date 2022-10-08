---
title: Limites e especificações para o Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: Este artigo descreve os limites, especificações e outros requisitos que se aplicam ao Microsoft Teams.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b34f22d5ef038eff44b5488588902d1a99af8676
ms.sourcegitcommit: fcedb958bf555d870215ae84fb83752304944716
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68486611"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limites e especificações para o Microsoft Teams

Este artigo descreve alguns dos limites, das especificações e de outros requisitos que se aplicam ao Teams.

## <a name="teams-and-channels"></a>Equipes e canais

|Recurso    | Limite máximo |
|-----------|---------------|
|Números de equipes que um usuário pode criar | Sujeito a um limite de objeto de 250&sup1;         |
|Número de equipes das quais um usuário pode ser membro|1.000&sup2;|
|Número de membros em uma equipe | 25.000<sup>6</sup>     |
|Número de proprietários por equipe | 100   |
|Número de equipes de toda a organização permitidas em um locatário | 5&sup2;     |
|Número de membros em uma [equipe de toda a organização](create-an-org-wide-team.md) | 10.000       |
|Número de equipes que um administrador global pode criar        |  500.000   |
|Número de equipes que uma organização do Microsoft 365 ou Office 365 pode ter    | 500,000&sup3;     |
|Número de canais por equipe    | 200 (inclui canais excluídos)<sup>4</sup>        |
|Número de canais privados por equipe    |30 (inclui canais excluídos)<sup>4</sup>        |
|Números de membros em um canal privado    |250|
|Tamanho máximo da lista de distribuição, grupo de segurança ou grupo do Microsoft 365 que pode ser importado para uma equipe    |3.500|
|Número máximo de membros em um grupo do Microsoft 365 que pode ser convertido em uma equipe    |10,000<sup>6</sup>     |
|Tamanho da postagem de conversa do canal | Aproximadamente 28 KB por postagem<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> Esse limite inclui equipes arquivadas. 

<sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.

<sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>5</sup> 28 KB é um limite aproximado porque inclui a própria mensagem (texto, links de imagens, etc.), @-menções, número de conectores e reações.

<sup>6</sup> Membros de canais compartilhados de fora da equipe contam com esse limite. Observe ainda que as menções de equipes/canal são bloqueadas em equipes com mais de 10.000 membros.

> [!NOTE]
> Para limites para canais compartilhados, consulte [Limites para canais compartilhados](/MicrosoftTeams/shared-channels#limits-for-shared-channels).

## <a name="messaging"></a>Mensagens

### <a name="chat"></a>Chat

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|Recurso  | Limite máximo  |
|---------|---------|
|Número de pessoas em um bate-papo particular <sup>1</sup>  | 250<sup>2</sup> |
|O número de pessoas em uma chamada de áudio ou vídeo do chat | 20 |
|Número de anexos de arquivo<sup>3</sup>  |10     |
|Tamanho do chat | Aproximadamente 28 KB por postagem <sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> Se o número de anexos exceder esse limite, você verá uma mensagem de erro.

<sup>4</sup> 28 KB é um limite aproximado porque inclui a própria mensagem (texto, links de imagens, etc.), menções com @ e reações.

### <a name="emailing-a-channel"></a>Enviar um email para um canal

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|Recurso  | Limite máximo  |
|---------|---------|
|Tamanho da mensagem <sup>1<sup> | 24 KB |
|Número de anexos de arquivo<sup>2</sup>  |20     |
|Tamanho de cada anexo de arquivo | Menor que 10 MB |
|Número de imagens embutidas<sup>2</sup> |50   |

> [!NOTE]
> Há um limite de limitação de quantos emails você pode enviar para um canal. O limite é de seis emails por dez segundos por canal por usuário e oito emails por dez segundos por locatário por usuário.
<sup>1</sup> Se a mensagem exceder esse limite, uma mensagem de visualização será gerada e o usuário será solicitado a baixar e exibir o email original no link fornecido.

<sup>2</sup> Se o número de anexos ou imagens exceder, você verá uma mensagem de erro.

Para obter mais informações, confira [Limites do Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>Nomes de canal

Os nomes de canal não podem conter os seguintes caracteres ou palavras:

|Tipo|Exemplo|
|---------|---------|
|Caracteres     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|Caracteres nesses intervalos    | 0 a 1F<br>80 a 9F        |
|Palavras     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 a COM9, LPT1 a LPT9, desktop.ini,  &#95;vti&#95;|

Os nomes de canal também não podem começar com um caractere de sublinhado (_), ponto final (.) ou terminar com um ponto final (.).

## <a name="meetings-and-calls"></a>Reuniões e chamadas

|Recurso     | Limite máximo |
|------------|---------------|
|Número de pessoas em uma reunião (podem conversar e telefonar)  | 1000, inclui GCC, GCCH e DoD, mas não A1 (300). **Somente exibição** permite que até 20.000 participantes, somente ouvintes, participem de uma reunião na qual o organizador tenha uma licença para E3/E5/A3/A5 SKU, bem como, Governo (GCC, GCC High, DoD). Em breve, a experiência somente exibição também estará disponível para seminários. Saiba mais sobre a [Experiência somente exibição](view-only-meeting-experience.md).<sup>1,2</sup>|
|O número de pessoas em uma chamada de áudio ou vídeo do chat | 20 |
|Tamanho máximo do arquivo do PowerPoint | 2 GB|
|As equipes mantêm [gravações de reunião](cloud-recording.md) que não são carregadas no Microsoft Stream, disponíveis para download local | 20 dias |
| Duração máxima da gravação da reunião | 4 horas ou 1,5 GB. Quando esse limite for atingido, a gravação terminará e será reiniciada automaticamente.
  
<sup>1</sup> Para obter a melhor experiência em grandes reuniões, seminários via web e eventos ao vivo, a Microsoft recomenda o uso da versão mais recente do cliente de área de trabalho do Microsoft Teams ou clientes móveis do Microsoft Teams.

<sup>2</sup> Apresentadores em grandes reuniões, seminários e eventos ao vivo devem usar o cliente de área de trabalho do Teams. Para mais dicas sobre como sediar grandes reuniões, veja[Melhores práticas para uma grande reunião no Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16).

> [!NOTE]
> Salas para sessão de grupo só podem ser criadas em reuniões com menos de 300 participantes. Além disso, a criação de salas para sessão de grupo em uma reunião limita automaticamente o número de participantes a 300. Aconselhe seus usuários finais a não iniciarem salas para sessão de grupo em reuniões onde esperam mais de 300 participantes. Para obter mais informações sobre grandes reuniões no Teams, compartilhe a orientação [Práticas recomendadas para uma grande reunião no Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16) com seus usuários finais.

### <a name="meeting-expiration"></a>Expiração de reunião

> [!NOTE]
> A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers, CVI coordinates, and/or underlying meeting policies and settings.

|Tipo de reunião  |A reunião expira após esse período  |Sempre que você iniciar ou atualizar uma reunião, a expiração será ampliada por esse período de tempo  |
|---------|---------|---------|
|Reunir agora     |Hora de início + oito horas         |Não disponível         |
|Regular sem hora de término     |Hora inicial + 60 dias         | 60 dias        |
|Regular com hora de término     |Hora de término + 60 dias         |60 dias         |
|Recorrente sem hora de término     |Hora inicial + 60 dias         |60 dias         |
|Recorrente com hora de término     |Hora de término da última ocorrência + 60 dias         |60 dias         |

> [!NOTE]
> As reuniões do Microsoft Teams têm um limite de tempo de 30 horas.

## <a name="teams-live-events"></a>Eventos Ao vivo do Teams

|Recurso     | Limite máximo |
|------------|---------------|
|Tamanho da audiência | 10.000 participantes |
|Duração do evento | 4 horas |
|Eventos simultâneos Ao vivo em execução em uma organização Microsoft 365 ou Office 365 <sup>1</sup> | 15 |

<sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.

Para obter mais informações sobre eventos ao vivo, acesse eventos [ao vivo do Teams](teams-live-events/plan-for-teams-live-events.md#teams-live-events). Confira também [Agendar um evento ao vivo do Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **O limite de eventos ao vivo do Microsoft 365 cresce**
>
> **Para continuar atendendo às necessidades de nossos clientes, estenderemos os aumentos temporários de limite para eventos ao vivo até 31 de dezembro de 2022, incluindo**:
>
>- Suporte a eventos para até 20.000 participantes
>- 50 eventos podem ser hospedados simultaneamente em um locatário
>- Duração do evento de 16 horas por transmissão
>
> Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Presença no Outlook

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).

## <a name="storage"></a>Armazenamento

Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

> [!NOTE]
> Cada [canal privado ](./private-channels.md)tem seu próprio site do Microsoft Office SharePoint Online (anteriormente chamado de "conjunto de sites").

If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)

Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.

|Recurso                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Armazenamento                 |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização mais 10 GB por licença adquirida   |1 TB por organização mais 10 GB por licença adquirida |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização           |
|Armazenamento de arquivos do Teams |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |
|Limite de upload de arquivos (por arquivo)    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |

Os canais são apoiados por pastas no site do Microsoft Office SharePoint Online (anteriormente chamado de "conjunto de sites") criado para a equipe, portanto, as guias de arquivo em Canais compartilham os limites de armazenamento da equipe a que pertencem.

Para mais informações, confira [Limites do SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Equipes de classe

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Uma equipe de classe é um tipo de modelo com aplicativos adicionais incluídos e com limites separados para o número de membros da equipe.

> [!NOTE]
> Usar equipes de classe requer uma [licença do Office 365 Education](https://www.microsoft.com/education/products/office).

Os limites para as equipes de classe estão listados na tabela a seguir:

|Recurso  |Limite máximo  |
|---------|---------|
|Número de membros em uma equipe    | Confira a seção [Equipes e canais](#teams-and-channels) deste artigo        |
|Número de membros para usar Tarefas em uma equipe de classe    | 300        |
|Número de membros para usar um Bloco de Anotações de Classe do OneNote em uma equipe de classe     |300         |

A class team can support more than 300 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.

## <a name="tags"></a>Marcas

|Recurso  |Limite máximo  |
|---------|---------|
|Número de marcas por equipe    | 100        |
|Número de marcas padrão sugeridas por equipe    | 25        |
|Número de membros da equipe atribuídos a uma marca    |200         |
|Número de marcas atribuídas a um usuário por equipe    |25         |

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
