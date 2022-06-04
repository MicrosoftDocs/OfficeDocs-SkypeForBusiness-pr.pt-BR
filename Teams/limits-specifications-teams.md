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
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16ca31652f3b5b9daa0216e683d80e6d9b0c809d
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886628"
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
|Tamanho máximo do grupo de distribuição, grupo de segurança ou grupo do Office 365 que pode ser importado para uma equipe    |3.500|
|Número máximo de membros em um grupo do Office 365 que pode ser convertido em uma equipe    |10,000<sup>6</sup>     |
|Tamanho da postagem de conversa do canal | Aproximadamente 28 KB por postagem<sup>5</sup> |

<sup>1</sup> Qualquer objeto de diretório no Azure Active Directory conta para este limite. Os administradores globais estão isentos desse limite, assim como os aplicativos que chamam o Microsoft Graph usando [permissões de aplicativo](/graph/permissions-reference).

<sup>2</sup> Esse limite inclui equipes arquivadas. 

<sup>3</sup> Para aumentar ainda mais o número de equipes, você deve entrar em contato com o suporte da Microsoft e solicitar um aumento adicional no número de objetos do Azure Active Directory em seu inquilino. O aumento só é feito para cenários de produção da vida real.

<sup>4</sup> Os canais excluídos podem ser restaurados dentro de 30 dias. Durante esses 30 dias, um canal excluído continua a ser contado para o limite de 200 canais ou 30 canais privados por equipe. Após 30 dias, um canal excluído e seu conteúdo são permanentemente excluídos e o canal não conta mais para o limite por equipe.

<sup>5</sup> 28 KB é um limite aproximado porque inclui a própria mensagem (texto, links de imagens, etc.), @-menções, número de conectores e reações.

<sup>6</sup> Membros de canais compartilhados de fora da equipe contam com esse limite. Observe ainda que as menções de equipes/canal são bloqueadas em equipes com mais de 10.000 membros.

> [!NOTE]
> Para limites de visualização de canais compartilhados, confira [Limites de canais compartilhados (visualização)](/MicrosoftTeams/shared-channels#limits-for-shared-channels-preview).

## <a name="messaging"></a>Mensagens

### <a name="chat"></a>Chat

Os usuários que participam de conversas que fazem parte da lista de bate-papo do Teams precisam ter uma caixa de correio no Exchange Online (baseada em nuvem) para um administrador pesquisar as conversas de bate-papo. Isso ocorre porque as conversas que fazem parte da lista de bate-papo ficam armazenadas nas caixas de correio baseadas em nuvem dos participantes do bate-papo. Se um participante do bate-papo não tiver uma caixa de correio do Exchange Online, o administrador não poderá pesquisar nem fazer uma retenção das conversas de bate-papo. Por exemplo, em uma implantação híbrida do Exchange, os usuários com caixas de correio locais podem participar de conversas que fazem parte da lista de bate-papo do Teams. No entanto, nesse caso, o conteúdo dessas conversas não é pesquisável e não pode ser colocado em espera porque os usuários não têm caixas de correio baseadas em nuvem. (Para obter mais informações, confira [Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md).)


|Recurso  | Limite máximo  |
|---------|---------|
|Número de pessoas em um bate-papo particular <sup>1</sup>  | 250<sup>2</sup> |
|O número de pessoas em uma chamada de áudio ou vídeo do chat | 20 |
|Número de anexos de arquivo<sup>3</sup>  |10     |
|Tamanho do chat | Aproximadamente 28 KB por postagem <sup>4</sup> |

<sup>1</sup> Se você tiver mais de 20 pessoais em um bate-papo, os seguintes recursos do bate-papo serão desabilitados: respostas automáticas do Outlook e mensagens de status do Teams; indicador de digitação; chamadas de áudio e vídeo; compartilhamento; confirmação de leitura. O botão "Configurar opções de entrega" (!) também é removido quando os chats de grupo privado contêm mais de 20 membros.

<sup>2</sup> Apenas 200 membros de cada vez podem ser adicionados a um chat em grupo. [Veja este artigo para mais informações](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat) .

<sup>3</sup> Se o número de anexos exceder esse limite, você verá uma mensagem de erro.

<sup>4</sup> 28 KB é um limite aproximado porque inclui a própria mensagem (texto, links de imagens, etc.), menções com @ e reações.

### <a name="emailing-a-channel"></a>Enviar um email para um canal

 Se os usuários quiserem enviar um email para um canal no Teams, eles devem usar o endereço de email do canal. Quando um email faz parte de um canal, qualquer pessoa pode respondê-lo para iniciar uma conversa. Aqui estão alguns dos limites aplicáveis de envio de email para um canal.

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
> O tamanho da mensagem, os anexos de arquivos e os limites de imagens embutidas são os mesmos em todas as licenças do Microsoft 365 e Office 365. O envio de emails em um canal não está disponível para organizações no Teams para Office GCC/GCCH/DOD.

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
> Um URL de reunião nunca para de funcionar. A expiração está relacionada apenas a qualquer número de discagem PSTN, coordenadas CVI e/ou políticas e configurações de reunião subjacentes.

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

<sup>1</sup> Você pode agendar quantos Eventos Ao vivo quiser, mas só pode executar 15 de cada vez. Assim que o produtor entra em um evento ao vivo, ele será considerado em andamento. O produtor que tentar participar do 16° evento ao vivo receberá uma mensagem de erro.

Para obter mais informações sobre eventos ao vivo do Teams e uma comparação entre eventos ao vivo do Teams e Transmissão de Reunião do Skype, vá para [Eventos ao vivo do Teams e Transmissão de Reunião do Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). Confira também [Agendar um evento ao vivo do Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **O limite de eventos ao vivo do Microsoft 365 cresce**
>
> **Para continuar dando suporte às necessidades de nossos clientes, estenderemos os aumentos de limites temporários para eventos ao vivo até 30 de junho de 2022, incluindo**:
>
>- Suporte a eventos para até 20.000 participantes
>- 50 eventos podem ser hospedados simultaneamente em um locatário
>- Duração do evento de 16 horas por transmissão
>
> Além disso, os Eventos ao Vivo com até 100.000 participantes podem ser planejados por meio do programa de assistência do Microsoft 365. A equipe avaliará cada solicitação e trabalhará com você para determinar opções que podem estar disponíveis. [Saiba Mais](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Presença no Outlook

A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior. Para saber mais sobre a presença no Teams, confira [Presença do usuário no Teams](presence-admins.md).

## <a name="storage"></a>Armazenamento

Cada equipe do Microsoft Teams tem um site de equipe no SharePoint Online e cada canal de uma equipe obtém uma pasta dentro da biblioteca de documentos padrão do site da equipe. Os arquivos compartilhados em uma conversa são adicionados automaticamente à biblioteca de documentos, e as permissões e as opções de segurança do arquivo definidas no SharePoint são refletidas automaticamente dentro do Teams.

> [!NOTE]
> Cada [canal privado ](./private-channels.md)tem seu próprio site do Microsoft Office SharePoint Online (anteriormente chamado de "conjunto de sites").

Se o SharePoint Online não está habilitado em seu locatário, os usuários do Microsoft Teams nem sempre poderão compartilhar arquivos em equipes. Os usuários em bate-papo particular também não podem compartilhar arquivos, pois o OneDrive for Business (que é vinculado à licença do SharePoint) é necessário para essa funcionalidade.

Ao armazenar os arquivos na biblioteca de documentos do SharePoint Online e no OneDrive for Business, todas as regras de conformidade configuradas no nível do locatário serão cumpridas. (Para saber mais, confira [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).)

Como o Teams é executado em um back-end do SharePoint Online para compartilhamento de arquivos, as limitações do SharePoint se aplicam à seção Arquivos em uma Equipe. Aqui estão os limites de armazenamento aplicáveis ao SharePoint Online.

|Recurso                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Armazenamento                 |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização mais 10 GB por licença adquirida   |1 TB por organização mais 10 GB por licença adquirida |1 TB por organização mais 10 GB por licença adquirida  |1 TB por organização           |
|Armazenamento de arquivos do Teams |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |Até 25 TB por conjunto de sites ou grupo |
|Limite de upload de arquivos (por arquivo)    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |250 GB    |

Os canais são apoiados por pastas no site do Microsoft Office SharePoint Online (anteriormente chamado de "conjunto de sites") criado para a equipe, portanto, as guias de arquivo em Canais compartilham os limites de armazenamento da equipe a que pertencem.

Para mais informações, confira [Limites do SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Equipes de classe

O Microsoft Teams para Educação fornece modelos projetados para cenários de ensino exclusivos, como o ensino da sala de aula. Mais informações sobre os tipos de equipe, incluindo as equipes de classe, estão disponíveis em [Escolha um tipo de equipe para colaborar no Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Uma equipe de classe é um tipo de modelo com aplicativos adicionais incluídos e com limites separados para o número de membros da equipe.

> [!NOTE]
> Usar equipes de classe requer uma [licença do Office 365 Education](https://www.microsoft.com/education/products/office).

Os limites para as equipes de classe estão listados na tabela a seguir:

|Recurso  |Limite máximo  |
|---------|---------|
|Número de membros em uma equipe    | Confira a seção [Equipes e canais](#teams-and-channels) deste artigo        |
|Número de membros para usar Tarefas em uma equipe de classe    | 300        |
|Número de membros para usar um Bloco de Anotações de Classe do OneNote em uma equipe de classe     |300         |

Uma equipe de classe pode dar suporte para mais de 300 membros. No entanto, se você planeja usar o aplicativo Tarefas ou o aplicativo Bloco de Anotações de Classe na sua equipe, será necessário manter o número de membros abaixo dos limites máximos acima.

## <a name="tags"></a>Marcas

|Recurso  |Limite máximo  |
|---------|---------|
|Número de marcas por equipe    | 100        |
|Número de marcas padrão sugeridas por equipe    | 25        |
|Número de membros da equipe atribuídos a uma marca    |100         |
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
