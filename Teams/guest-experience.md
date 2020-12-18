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
description: Este artigo descreve as funcionalidades do Microsoft Teams disponíveis para convidados.
ms.openlocfilehash: 25ea63de9bcdc85e0f7b81e382c2c9bcd057c629
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49661886"
---
# <a name="guest-experience-in-teams"></a>Experiência de convidado no Teams

Quando um convidado é solicitado a entrar em uma equipe, ele recebe uma mensagem de boas-vindas por e-mail. Essa mensagem contém algumas informações sobre a equipe e o que esperar agora que ele é um membro. O convidado deve aceitar o convite selecionando **Abrir Microsoft Teams** na mensagem de e-mail antes de poder acessar a equipe e seus canais.
    
![Captura de tela mostrando um exemplo de uma mensagem de email de boas-vindas](media/guest-experience-image1.png)
    
Todos os membros da equipe veem uma mensagem no tópico do canal anunciando que o proprietário da equipe adicionou um convidado e informou o nome do convidado. Todos da equipe podem identificar facilmente quem é um convidado. Uma marca no canto superior direito do encadeamento de canal indica o número de convidados na equipe e um rótulo de **(Convidado)** é exibido ao lado do nome de cada convidado.

![Captura de tela mostrando o rótulo que indica o número de convidados na equipe](media/guest-experience-image2.png)

Confira estes vídeos sobre a experiência de convidado no Teams:
- [Participe de uma equipe como convidado](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Participe de uma reunião do Teams com convidados](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Recursos do convidado e membro da equipe

A tabela a seguir compara as funcionalidades disponíveis no Teams para os membros da equipe de uma organização e seus convidados. Os administradores do Teams controlam os recursos disponíveis aos convidados.

| Recurso no Teams | Usuário do Teams na organização | Guest |
|:-----|:-----|:-----|
|Criar um canal  <br/>  *Os proprietário de equipes controlam essa configuração.*  <br/> |&#x2713;|&#x2713;|
|Participar de um bate-papo privado  <br/> |&#x2713;|&#x2713;|
|Participar de uma conversa de canal  <br/> |&#x2713;|&#x2713;|
|Publicar, excluir e editar mensagens  <br/> |&#x2713;|&#x2713;|
|Compartilhar um arquivo de canal  <br/> |&#x2713;|&#x2713;|
|Acessar arquivos do SharePoint<br/> |&#x2713;|&#x2713;|
|Anexar arquivos<br/> |&#x2713;|Apenas conversas da equipe|
|Baixar arquivos particulares de chat<br/> |&#x2713;|&#x2713;|
|Pesquisar dentro de arquivos<br/> |&#x2713;||
|Compartilhar um arquivo de bate-papo  <br/> |&#x2713;||
|Adicionar aplicativos (guias, bots ou conectores)  <br/> |&#x2713;||
|Crie reuniões ou acesse agendas  <br/> |&#x2713;||
|Acessar o armazenamento do OneDrive for Business  <br/> |&#x2713;||
|Criar políticas de acesso de convidados de equipes/canais de todos os locatários  <br/> |&#x2713;||
|Convidar um usuário de fora do domínio da organização do Microsoft 365 ou do Office 365 <br/>  *Os proprietários do Teams controlam essa configuração.*  <br/> <br/> |&#x2713;||
|Criar uma equipe  <br/> |&#x2713;||
|Descobrir e entrar em uma equipe pública  <br/> |&#x2713;||
|Visualizar o organograma  <br/> |&#x2713;||
|Usar a tradução de mensagens embutida  <br/> |&#x2713;||
|Tornar-se proprietário da equipe  <br/> |&#x2713;||

A tabela a seguir mostra os recursos de chamada e reunião disponíveis para convidados, em comparação com outros tipos de usuários.

| Recurso de chamada | Guest | Usuário E1 e E3 | Usuários E5 e Enterprise Voice |
| --------------- | ----- | -------------- | -------------- |
| Chamadas de VOIP | Sim | Sim | Sim |
| Chamadas de grupo | Sim | Sim | Sim |
| Controles principais de chamada suportados (segurar, ativar mudo, vídeo, compartilhamento de tela) | Sim | Sim | Sim |
| Destino de transferência | Sim | Sim | Sim |
| Pode transferir uma chamada | Sim | Sim | Sim |
| Pode transferência consultiva | Sim | Sim | Sim |
| Pode adicionar outros usuários a uma chamada via VOIP | Sim | Sim | Sim |
| Pode adicionar usuários por telefone a uma chamada | Não | Não | Sim |
| Destino de encaminhamento | Não | Sim | Sim |
| Destino do grupo de chamadas | Não | Sim | Sim |
| Destino não respondido | Não | Sim | Sim |
| Pode ser o destino de uma chamada federada | Não | Sim | Sim |
| Pode fazer uma chamada federada | Não | Sim | Sim |
| Pode encaminhar suas chamadas imediatamente | Não | Não | Sim |
| Pode ligar simultaneamente suas chamadas | Não | Não | Sim |
| Pode direcionar suas chamadas não respondidas | Não | Não | Sim |
| Chamadas perdidas podem ir para a caixa postal | Não | Não<sup>1</sup> |Sim |
| Tem um número de telefone que possa receber chamadas | Não | Não | Sim |
| Pode discar números de telefone | Não | Não | Sim |
| Pode acessar as configurações de chamada | Não | Não | Sim |
| Pode alterar a saudação da caixa postal | Não | Não<sup>1</sup> | Sim |
| Pode alterar toques | Não | Não  | Sim |
| Suporte a TTY | Não | Não | Sim |
| Pode ter delegados | Não | Não | Sim |
|  Pode ser um representante | Não | Não | Sim |

<sup>1</sup> Este recurso estará disponível em breve.

> [!NOTE]
> A política de **restrições de acesso de usuário convidado** no Azure AD Directory (Azure AD) determina permissões para convidados em seu diretório. Há três opções de políticas.
>  - Os **Usuários convidados têm o mesmo acesso que os membros (mais inclusivos)** às configuração, o que significa que os convidados têm o mesmo acesso aos dados do diretório como usuários regulares do seu diretório.
>  - Os **Usuários convidados têm acesso limitado a propriedades e associação de objetos do diretório** das configurações, o que significa que os convidados não têm permissões para determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório usando o Microsoft Graph.
>  - O **Acesso de usuário convidado é restrito a propriedades e associações de seus próprios objetos de diretório (mais restritivos)** da configuração, o que significa que os convidados só podem acessar seus próprios objetos de diretório.
>
>Para saber mais, confira [Quais são as permissões de usuário padrão no Azure Active Directory?](https://go.microsoft.com/fwlink/?linkid=2135493)

## <a name="related-topics"></a>Tópicos relacionados

[Deixar uma organização como um convidado](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)
