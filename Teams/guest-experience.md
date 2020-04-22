---
title: Como é a experiência do convidado
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Conheça a funcionalidade do Microsoft Teams disponível para usuários convidados.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60891c2e5283b8e9cdaa9e8d7852768bbb52d8aa
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776926"
---
<a name="what-the-guest-experience-is-like"></a>Como é a experiência do convidado
=================================

Quando um convidado é convidado a ingressar em uma equipe, ele recebe uma mensagem de boas-vindas. Essa mensagem inclui algumas informações sobre a equipe e o que esperar agora que elas são membro. O convidado deve aceitar o convite selecionando **abrir o Microsoft Teams** na mensagem de email para que ele possa acessar a equipe e seus canais.
    
![Captura de tela mostrando um exemplo de uma mensagem de boas-vindas](media/guest-experience-image1.png)
    
Todos os membros da equipe veem uma mensagem no tópico do canal anunciando que o proprietário da equipe adicionou um convidado e informou o nome do convidado. Todos da equipe podem identificar facilmente quem é um convidado. Conforme mostrado na captura de tela a seguir de uma equipe de exemplo, uma faixa indica que "esta equipe tem convidados" e um rótulo **(convidado)** aparece ao lado do nome de cada convidado.
    
![Captura de tela mostrando usuários convidados de notificação de cabeçalho](media/guest-experience-image2.png "A captura de tela mostra uma parte do canal de marketing da Northwind Traders, com a notificação na faixa superior informando que a equipe tem convidados e os usuários que os convidados são identificados com a palavra GUEST ao lado do nome.")

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Comparação entre os recursos de membro da equipe e de convidado

A tabela a seguir compara a funcionalidade do teams disponível para os membros da equipe da organização e seus convidados.

|**Recurso no Teams**|**Usuário do Teams na organização**|**Convidado usuário**|
|:-----|:-----|:-----|
|Criar um canal  <br/>  *Os proprietário de equipes controlam essa configuração.*  <br/> |&#x2713;|&#x2713;|
|Participar de um bate-papo privado  <br/> |&#x2713;|&#x2713;|
|Participar de uma conversa de canal  <br/> |&#x2713;|&#x2713;|
|Publicar, excluir e editar mensagens  <br/> |&#x2713;|&#x2713;|
|Compartilhar um arquivo de canal  <br/> |&#x2713;|&#x2713;|
|Compartilhar um arquivo de bate-papo  <br/> |&#x2713;||
|Adicionar aplicativos (guias, bots ou conectores)  <br/> |&#x2713;||
|Criar reuniões ou agendas do Access  <br/> |&#x2713;||
|Acessar o armazenamento do OneDrive for Business  <br/> |&#x2713;||
|Criar políticas de acesso de convidados de equipes/canais de todos os locatários  <br/> |&#x2713;||
|Convidar um usuário para fora do domínio da organização do Office 365 <br/>  *Os proprietário de equipes controlam essa configuração.*  <br/> <br/> |&#x2713;||
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
> Os administradores do Office 365 controlam os recursos disponíveis aos convidados. 

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="how-do-i-leave-an-organization-that-ive-been-invited-to"></a>Como faço para sair de uma organização para a qual foi convidado?
Se você tiver sido convidado para uma organização da qual não deseja ser convidado, pode optar por sair da organização. Para obter mais informações, vá para [deixar uma organização como um usuário convidado](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization). Você também pode solicitar que o administrador da organização o remova do locatário. Observe que, em ambos os casos, você precisará ser convidado novamente para o locatário se quiser acessar a organização no futuro.

### <a name="do-guests-have-the-same-capabilities-as-team-members"></a>Os convidados têm os mesmos recursos que os membros da equipe?
Não. Para obter mais informações sobre o que um convidado pode e não pode fazer, acesse a [comparação de recursos de convidados e de membros da equipe](#comparison-of-team-member-and-guest-capabilities) neste artigo.

### <a name="do-guests-have-access-to-onedrive-for-business"></a>Os convidados têm acesso ao OneDrive for Business?
Não.

### <a name="do-guests-have-access-to-sharepoint-files"></a>Os convidados têm acesso aos arquivos do SharePoint?
Sim.

### <a name="can-guests-search-within-files"></a>Os convidados podem pesquisar dentro dos arquivos?
Não.

### <a name="can-guests-attach-files"></a>Os convidados podem anexar arquivos?
Sim, um convidado pode anexar arquivos destas duas maneiras:

   - Selecione **arquivos** no painel esquerdo e navegue até o local do arquivo.
   - Carregar arquivos do computador.

### <a name="can-a-guest-download-a-file-in-a-private-chat"></a>Um convidado pode baixar um arquivo em um chat particular?
Sim, eles podem receber um arquivo de um membro em um chat particular e, em seguida, baixá-lo para a área de trabalho.
