---
title: Limites e especificações para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Este artigo descreve os limites, especificações e outros requisitos que se aplicam ao Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 178dc23403a637e15bb8c01b18e03fb5c86477dc
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522338"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limites e especificações para o Microsoft Teams

Este artigo descreve alguns dos limites, das especificações e de outros requisitos que se aplicam ao Teams.

## <a name="teams-and-channels"></a>Equipes e canais

|Recurso    | Limite máximo |
|-----------|---------------|
|Números de equipes que um usuário pode criar | Sujeito a um limite de objeto de 250&sup1;         |
|Número de equipes das quais um usuário pode ser membro|1.000|
|Número de membros em uma equipe | 10.000       |
|Número de proprietários por equipe | 100   |
|Número de equipes de toda a organização permitidas em um locatário | 5     |
|Número de membros em uma [equipe de toda a organização](create-an-org-wide-team.md) | 5.000       |
|Número de equipes que um administrador global pode criar        |  500.000   |
|Número de equipes que uma organização do Microsoft 365 ou Office 365 pode ter    | 500.000&sup2;     |
|Número de canais por equipe    | 200 (inclui canais excluídos)&sup3;         |
|Número de canais privados por equipe    |30|
|Números de membros em um canal privado    |250|
|Tamanho da postagem de conversa do canal | Aproximadamente 28 KB pela postagem <sup>4</sup> |

<sup>1</sup> Qualquer objeto de diretório no Azure Active Directory conta para este limite. Os administradores globais estão isentos desse limite, assim como os aplicativos que chamam o Microsoft Graph usando as [permissões de aplicativo](https://docs.microsoft.com/graph/permissions-reference).

<sup>2</sup> Esse limite inclui equipes arquivadas.

<sup>3</sup> Os canais excluídos podem ser restaurados dentro de 30 dias. Durante esses 30 dias, um canal excluído continua a ser contado no limite de 200 canais por equipe. Depois de 30 dias, um canal e seu conteúdo excluídos serão permanentemente excluídos e o canal deixará de contar com o limite de 200 canais por equipe.

<sup>4</sup> 28 KB é um limite aproximado porque inclui a própria mensagem (texto, links de imagens, etc.), @-menções, número de conectores e reações.

## <a name="messaging"></a>Mensagens

### <a name="chat"></a>Chat

Os usuários que participam de conversas que fazem parte da lista de bate-papo do Teams precisam ter uma caixa de correio no Exchange Online (baseada em nuvem) para um administrador pesquisar as conversas de bate-papo. Isso ocorre porque as conversas que fazem parte da lista de bate-papo ficam armazenadas nas caixas de correio baseadas em nuvem dos participantes do bate-papo. Se um participante de bate-papo não tiver uma caixa de correio do Exchange Online, o administrador não poderá pesquisar nem fazer uma retenção das conversas de bate-papo. Por exemplo, em uma implantação híbrida do Exchange, os usuários com caixas de correio locais podem participar de conversas que fazem parte da lista de bate-papo do Teams. No entanto, nesse caso, o conteúdo dessas conversas não é pesquisável e não pode ser colocado em espera porque os usuários não têm caixas de correio baseadas em nuvem. (Para saber mais, confira [Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md).)

O bate-papo do Teams funciona em um back-end do Microsoft Exchange, para que os limites de mensagens do Exchange sejam aplicados à função de bate-papo dentro do Teams.

|Recurso  | Limite máximo  |
|---------|---------|
|Número de pessoas em um bate-papo particular <sup>1</sup>  | 250<br><br>**Observação:** para O Teams Governamental (GCC, GCC Alta, DoD), o limite ainda é 100. Atualizaremos este artigo quando o limite de nuvem governamental aumentar de 100 para 250.    |
|O número de pessoas em uma chamada de áudio ou vídeo do chat | 20 |
|Número de anexos de arquivo<sup>2</sup>  |10     |
|Tamanho do chat | Aproximadamente 28 KB pela postagem <sup>3</sup> |

<sup>1</sup> Se você tiver mais de 20 pessoais em um bate-papo, os seguintes recursos do bate-papo serão desabilitados: respostas automáticas do Outlook e mensagens de status do Teams; indicador de digitação; chamadas de áudio e vídeo; compartilhamento; confirmação de leitura. O botão "Configurar opções de entrega" (!) também é removido quando os chats de grupo privado contêm mais de 20 membros.

<sup>2</sup> Se o número de anexos exceder esse limite, você verá uma mensagem de erro.

<sup>3</sup> 28 KB é um limite aproximado porque inclui a própria mensagem (texto, links de imagens, etc.), @-menções e reações.

### <a name="emailing-a-channel"></a>Enviar um email para um canal

 Se os usuários quiserem enviar um email para um canal no Teams, eles devem usar o endereço de email do canal. Quando um email faz parte de um canal, qualquer pessoa pode respondê-lo para iniciar uma conversa. Aqui estão alguns dos limites aplicáveis de envio de email para um canal.

|Recurso  | Limite máximo  |
|---------|---------|
|Tamanho da mensagem <sup>1<sup> | 24 KB |
|Número de anexos de arquivo<sup>2</sup>  |20     |
|Tamanho de cada anexo de arquivo | Menor que 10 MB |
|Número de imagens embutidas<sup>2</sup> |50   |

<sup>1</sup> Se a mensagem exceder esse limite, uma mensagem de visualização será gerada e o usuário será solicitado a baixar e exibir o email original no link fornecido.

<sup>2</sup> Se o número de anexos ou imagens exceder, você verá uma mensagem de erro.

Para obter mais informações, confira [Limites do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> O tamanho da mensagem, os anexos de arquivos e os limites de imagens embutidas são os mesmos em todas as licenças do Microsoft 365 e Office 365.

## <a name="channel-names"></a>Nomes de canal

Os nomes de canal não podem conter os seguintes caracteres ou palavras.

|||
|---------|---------|
|Caracteres     | ~ # % & * { } + / \ : < > ? &#124; ' " , .        |
|Caracteres nesses intervalos    | 0 a 1F<br>80 a 9F        |
|Palavras     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 a COM9, LPT1 a LPT9, desktop.ini,  &#95;vti&#95;|

Os nomes de canal também não podem começar com um caractere de sublinhado (_), ponto final (.) ou terminar com um ponto final (.).

## <a name="meetings-and-calls"></a>Reuniões e chamadas

> [!IMPORTANT]
> Em abril, [anunciamos](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-in-microsoft-teams-april-2020/ba-p/1347929) que os aumentos de limite padrão temporário seriam habilitados para o Microsoft 365 Live Events para ajudá-los a dar suporte melhor aos clientes até o dia 1 de julho. Para continuar atendendo às necessidades dos clientes, estenderemos os limites padrão temporários até o dia 1 de outubro de 2020. Os eventos dinâmicos hospedados no Teams, no Stream e no Yammer continuarão a dar suporte temporário a eventos para até 20.000 participantes, 16 horas de duração e 50 eventos que ocorram simultaneamente. Além disso, os clientes podem hospedar um evento ao vivo no Stream para até 100.000 participantes quando planejado pelo [programa de assistência Microsoft Live Events](https://resources.techcommunity.microsoft.com/live-events/assistance/).

|Recurso     | Limite máximo |
|------------|---------------|
|Número de pessoas em uma reunião (podem conversar e telefonar)  |300. <br><br>**Observação:** Para o Teams Governamental (GCC, GCC Alta, DoD), o limite ainda é 250. Atualizaremos este artigo quando o limite de nuvem governamental aumentar de 250 para 300 e der suporte a transportadores de reunião.   |
|Número de pessoas em uma reunião (podem conversar e telefonar)  | 300 |
|O número de pessoas em uma chamada de áudio ou vídeo do chat | 20 |
|Tamanho máximo do arquivo do PowerPoint | 2GB|
|As equipes mantêm [gravações de reunião](cloud-recording.md) que não são carregadas no Microsoft Stream, disponíveis para download local | 20 dias |

### <a name="meeting-expiration"></a>Expiração de reunião

|Tipo de reunião  |A reunião expira após esse período  |Sempre que você iniciar ou atualizar uma reunião, a expiração será ampliada por esse período de tempo  |
|---------|---------|---------|
|Reunir agora     |Hora de início + oito horas         |Não disponível         |
|Regular sem hora de término     |Hora inicial + 60 dias         | 60 dias        |
|Regular com hora de término     |Hora de término + 60 dias         |60 dias         |
|Recorrente sem hora de término     |Hora inicial + 60 dias         |60 dias         |
|Recorrente com hora de término     |Hora de término da última ocorrência + 60 dias         |60 dias         |

> [!NOTE]
> As reuniões do Microsoft Teams têm um limite de tempo de 24 horas.

## <a name="teams-live-events"></a>Eventos ao vivo do Teams

|Recurso     | Limite máximo |
|------------|---------------|
|Tamanho da audiência | 10.000 participantes |
|Duração do evento | 4 horas |
|Eventos ao vivo simultâneos em execução em uma organização do Microsoft 365 ou Office 365 <sup>1</sup> | 15 |

<sup>1</sup> Você pode agendar o número de eventos que desejar, mas é possível executar apenas 15 por vez. Assim que o produtor entra em um evento ao vivo, ele será considerado em andamento. O produtor que tentar se entrar no décimo-sexto evento ao vivo receberá uma mensagem de erro.

Para saber mais sobre eventos ao vivo e uma comparação dos eventos ao vivo do Teams para a Transmissão de Reunião do Skype, vá para [Eventos ao vivo do Teams e Transmissão de Reunião do Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

> [!IMPORTANT]
> **O limite de eventos ao vivo do Microsoft 365 cresce**
>
> Para ajudar os clientes a atender às necessidades de comunicação que mudam rapidamente, os eventos ao vivo do Microsoft 365 aumentarão temporariamente os limites padrão até 1º de outubro de 2020, para eventos ao vivo hospedados no Teams. Os seguintes aumentos foram lançados:
>
> - Limite de participantes: os eventos podem dar suporte a no máximo 20.000 participantes
> - Eventos simultâneos: 50 eventos podem ser hospedados simultaneamente em um locatário
> - Duração do evento: a duração do evento aumentou para 16 horas por transmissão

## <a name="presence-in-outlook"></a>Presença no Outlook

A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior. Para saber mais sobre a presença no Teams, confira [Presença do usuário no Teams](presence-admins.md).

## <a name="storage"></a>Armazenamento

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online, e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

> [!NOTE]
> Cada [canal privado](https://docs.microsoft.com/microsoftteams/private-channels) tem seu próprio conjunto de sites do SharePoint.

Se o SharePoint Online não está habilitado em seu locatário, os usuários do Microsoft Teams nem sempre poderão compartilhar arquivos em equipes. Os usuários no bate-papo particular também não podem compartilhar arquivos, pois o OneDrive for Business (que é vinculado à licença do SharePoint) é necessário para essa funcionalidade.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível tenant serão cumpridas. (Para saber mais, confira [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).)

Como o Teams é executado em um back-end do SharePoint Online para compartilhamento de arquivos, as limitações do SharePoint se aplicam à seção Arquivos em uma Equipe. Estes são os limites de armazenamento aplicáveis ao SharePoint Online.

|Recurso                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Armazenamento                 |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização mais 10 GB por licença adquirida   |1 TB por organização mais 10 GB por licença adquirida |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização           |
|Armazenamento de arquivos do Teams |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |
|Limite de upload de arquivos (por arquivo)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Os canais são apoiados por pastas dentro do conjunto de sites do SharePoint Online criado para a equipe, para que as guias de arquivo dentro de Canais compartilhem os limites de armazenamento da equipe a que pertencem.

Para mais informações, confira [Limites do SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="tags"></a>Marcas

|Recurso  |Limite máximo  |
|---------|---------|
|Número de marcas por equipe    | 100        |
|Número de marcas padrão sugeridas por equipe    | 25        |
|Número de membros da equipe atribuídos a uma marca    |100         |
|Número de marcas atribuídas a um usuário    |25         |

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
