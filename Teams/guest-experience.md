---
title: Experiência de convidado no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Este artigo descreve a funcionalidade do Microsoft Teams disponível para usuários convidados.
ms.openlocfilehash: a2c4bcf380eb90f7c0a00c8f6f4f9141b80f8460
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030287"
---
# <a name="guest-experience-in-teams"></a>Experiência de convidado no Microsoft Teams

Quando um convidado é convidado a ingressar em uma equipe, ele recebe uma mensagem de boas-vindas. Essa mensagem inclui algumas informações sobre a equipe e o que esperar agora que elas são membro. O convidado deve aceitar o convite selecionando **abrir o Microsoft Teams** na mensagem de email para que ele possa acessar a equipe e seus canais.
    
![Captura de tela mostrando um exemplo de uma mensagem de email de boas-vindas](media/guest-experience-image1.png)
    
Todos os membros da equipe veem uma mensagem no tópico do canal anunciando que o proprietário da equipe adicionou um convidado e informou o nome do convidado. Todos da equipe podem identificar facilmente quem é um convidado. Uma marca no canto superior direito do segmento de canal indica o número de convidados na equipe e um rótulo de a **(convidado)** exibido ao lado do nome de cada convidado.

![Captura de tela mostrando a marca que indica o número de convidados na equipe](media/guest-experience-image2.png)

Confira estes vídeos sobre a experiência de convidado no Microsoft Teams:
- [Ingressar em uma equipe como um convidado](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Ingressar em uma reunião do teams com convidados](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Comparação entre os recursos de membro da equipe e de convidado

A tabela a seguir compara a funcionalidade do teams disponível para os membros da equipe da organização e seus convidados. Os administradores de equipe controlam os recursos disponíveis para os convidados.

|**Recurso no Teams**|**Usuário do Teams na organização**|**Convidado usuário**|
|:-----|:-----|:-----|
|Criar um canal  <br/>  *Os proprietário de equipes controlam essa configuração.*  <br/> |&#x2713;|&#x2713;|
|Participar de um bate-papo privado  <br/> |&#x2713;|&#x2713;|
|Participar de uma conversa de canal  <br/> |&#x2713;|&#x2713;|
|Publicar, excluir e editar mensagens  <br/> |&#x2713;|&#x2713;|
|Compartilhar um arquivo de canal  <br/> |&#x2713;|&#x2713;|
|Acessar arquivos do SharePoint<br/> |&#x2713;|&#x2713;|
|Anexar arquivos<br/> |&#x2713;|&#x2713;|
|Baixar arquivos de chat particulares<br/> |&#x2713;|&#x2713;|
|Pesquisar em arquivos<br/> |&#x2713;||
|Compartilhar um arquivo de bate-papo  <br/> |&#x2713;||
|Adicionar aplicativos (guias, bots ou conectores)  <br/> |&#x2713;||
|Criar reuniões ou agendas do Access  <br/> |&#x2713;||
|Acessar o armazenamento do OneDrive for Business  <br/> |&#x2713;||
|Criar políticas de acesso de convidados de equipes/canais de todos os locatários  <br/> |&#x2713;||
|Convidar um usuário para fora do domínio da organização do Microsoft 365 ou do Office 365 <br/>  *Os proprietário de equipes controlam essa configuração.*  <br/> <br/> |&#x2713;||
|Criar uma equipe  <br/> |&#x2713;||
|Descobrir e entrar em uma equipe pública  <br/> |&#x2713;||
|Visualizar o organograma  <br/> |&#x2713;||
|Usar a tradução embutida  <br/> |&#x2713;||
|Tornar-se proprietário da equipe  <br/> |&#x2713;||

A tabela a seguir mostra os recursos de chamada e reunião disponíveis para convidados, em comparação com outros tipos de usuários.

| Recurso de chamada | Convite | Usuário E1 e E3 | E5 e usuário do Enterprise Voice |
| --------------- | ----- | -------------- | -------------- |
| Chamadas de VOIP | Sim | Sim | Sim |
| Chamadas em grupo | Sim | Sim | Sim |
| Controles de chamada de núcleo com suporte (espera, mudo, ativar/desativar vídeo, compartilhamento de tela) | Sim | Sim | Sim |
| Destino da transferência | Sim | Sim | Sim |
| Pode transferir uma chamada | Sim | Sim | Sim |
| Pode transferir consultoria | Sim | Sim | Sim |
| Pode adicionar outros usuários a uma chamada via VOIP | Sim | Sim | Sim |
| Pode adicionar usuários por número de telefone a uma chamada | Não | Não | Sim |
| Encaminhar alvo | Não | Sim | Sim |
| Destino do grupo de chamadas | Não | Sim | Sim |
| Alvo não respondido | Não | Sim | Sim |
| Pode ser o destino de uma chamada federada | Não | Sim | Sim |
| Pode fazer uma chamada federada | Não | Sim | Sim |
| Pode encaminhar suas chamadas imediatamente | Não | Não | Sim |
| Pode ligar simultaneamente para suas chamadas | Não | Não | Sim |
| Pode encaminhar as chamadas não atendidas | Não | Não | Sim |
| Chamadas perdidas podem ser enviadas para o correio de voz | Não | Não<sup>1</sup> |Sim |
| Ter um número de telefone que possa receber chamadas | Não | Não | Sim |
| Pode discar números de telefone | Não | Não | Sim |
| Pode acessar as configurações de chamada | Não | Não | Sim |
| Pode alterar a saudação da caixa postal | Não | Não<sup>1</sup> | Sim |
| Pode alterar toques | Não | Não  | Sim |
| Suporte a TTY | Não | Não | Sim |
| Pode ter representantes | Não | Não | Sim |
|  Pode ser um representante | Não | Não | Sim |

<sup>1</sup> esse recurso estará disponível em breve.

> [!NOTE]
> A política de **restrições de acesso do usuário convidado** no Azure Active Directory (Azure AD) determina permissões para convidados em seu diretório. Há três opções de políticas.
>  - Os **Usuários convidados têm o mesmo acesso que os membros (mais inclusivos)** às configuração, o que significa que os convidados têm o mesmo acesso aos dados do diretório como usuários regulares do seu diretório.
>  - Os **Usuários convidados têm acesso limitado a propriedades e associação de objetos do diretório** das configurações, o que significa que os convidados não têm permissões para determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório usando o Microsoft Graph.
>  - O **Acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório (mais restritivos)** da configuração, o que significa que os convidados só podem acessar seus próprios objetos de diretório.
>
>Para saber mais, confira [Quais são as permissões de usuário padrão no Azure Active Directory?](https://go.microsoft.com/fwlink/?linkid=2135493)

## <a name="related-topics"></a>Tópicos relacionados

[Deixar uma organização como um usuário convidado](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)
