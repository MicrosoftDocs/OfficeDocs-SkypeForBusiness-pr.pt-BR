---
title: Colocar um usuário ou uma equipe do Microsoft Teams em retenção legal
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a colocar um usuário Microsoft Teams equipe em espera legal usando o Centro de conformidade do Microsoft 365 e saiba o que precisa de uma responsabilidade legal com base nos requisitos de dados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b3ea009e538b8796a9e55b277dc4ec12f5a3a4
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711555"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Colocar um usuário ou uma equipe do Microsoft Teams em retenção legal

Quando existe uma expectativa razoável de litígio, as organizações são obrigadas a preservar as informações armazenadas eletronicamente (ESI), incluindo Teams mensagens de chat relevantes para o caso. As organizações podem precisar preservar todas as mensagens relacionadas a uma investigação específica ou a uma pessoa específica. Este artigo discutirá o uso de uma ressarção legal para preservar o conteúdo Microsoft Teams. Para preservar o conteúdo em outros serviços Microsoft 365, consulte [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> Em fevereiro de 2020, acariámos a responsabilidade legal para canais privados. Chats de canal privado são armazenados em caixas de correio de usuário, enquanto chats de canal padrão são armazenados na caixa de correio associada à equipe pai. Se já houver uma suspensão legal para uma caixa de correio de usuário, a política de espera será aplicada automaticamente às mensagens de canal privado armazenadas nessa caixa de correio. Não há mais nenhuma ação necessária para um administrador ativar isso. Também há suporte para a responsabilidade legal dos arquivos compartilhados em canais privados.

Dentro Microsoft Teams, uma equipe inteira ou usuários selecionados podem ser colocados em espera legal. Isso garantirá que todas as mensagens que foram trocadas nessas equipes (incluindo canais privados e compartilhados) ou mensagens trocadas por essas pessoas sejam descobertas pelos gerentes de conformidade ou administradores Teams da organização.

> [!NOTE]
> A colocação de um usuário em retenção não coloca automaticamente um grupo em retenção ou vice-versa.
> As notificações enviadas em feeds de atividade não podem ser colocadas em espera.

Para colocar um usuário ou uma equipe em uma responsabilidade legal em um caso de Descoberta Interna Principal:

1. Vá para o [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com). Quando você cria um novo caso, você é apresentado com a opção de colocar caixas de correio ou sites em espera.

2. Vá para **eDiscoveryCore** >  e crie uma ocorrência clicando em **Criar uma ocorrência**. Depois que o caso for criado, abra-o.
  
   ![Microsoft Teams guia Descoberta Online está selecionada, mostrando o botão Criar uma ocorrência.](media/LegalHold1.png)

   > [!NOTE]
   > Você também pode colocar um usuário em uma responsabilidade associada a um Advanced eDiscovery caso. Para obter mais informações, consulte [Manage holds in Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Vá até a guia **Retém** no menu superior e clique **em Criar** para criar uma espera. Colocar um usuário ou uma equipe em espera preserva todas as mensagens trocadas por esses usuários. Quando você cria um novo caso, você é apresentado com a opção de colocar caixas de correio ou sites em espera.

   ![Uma imagem mostrando a guia Retém selecionada e o botão Criar abaixo.](media/LegalHold2.png)

   1. **Nomeia sua espera**. Selecione um nome descritivo e exclusivo para a espera que você vai criar.
  
       ![Esta captura de tela mostra a guia Nome da sua espera, onde você pode inserir um nome e uma descrição para a bloqueio que você está criando.](media/LegalHold3.png)

   2. **Escolha local**. Escolha se deseja que a responsabilidade seja aplicada em um usuário ou em uma Equipe inteira (uma ressarção não pode ser aplicada em canais individuais por enquanto). Se um usuário estiver em espera, todas as mensagens serão preservadas, incluindo mensagens em chats 1:1, chats de grupo e canais privados. As mensagens em canais padrão e compartilhados são preservadas quando a equipe pai é colocada em espera.

      ![Escolha os locais de dados que você deseja colocar em espera.](media/LegalHold4.png)

   3. **Criar consulta**. Você pode personalizar a espera se quiser mais granularidade na política de espera. Por exemplo, você pode especificar palavras-chave a serem pesquisadas, ou você pode adicionar mais condições, que precisariam ser atendidas para que a espera entre em vigor.

   4. **Revise suas configurações antes** de criar a espera.

Depois que a espera for criada, você poderá pesquisar o conteúdo mantido pela política de espera. Para obter mais informações, [consulte Conduct an eDiscovery investigation in Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Quando um usuário ou grupo é colocado em espera, todas as cópias de conformidade das mensagens são preservadas. Por exemplo, se um usuário postar uma mensagem em um canal e modificar a mensagem, ambas as cópias da mensagem serão preservadas. Sem a espera, somente a mensagem mais recente é preservada.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Locais de conteúdo para colocar em espera para preservar Teams conteúdo

Como um guia útil, use a tabela a seguir para entender quais locais de conteúdo (como uma caixa de correio ou um site) colocar em espera para preservar diferentes tipos de conteúdo Teams conteúdo.

|Cenário  |Local do conteúdo  |
|---------|---------|
|Mensagens de chat para um usuário (por exemplo, chats 1:1, chats de grupo 1:N e conversas de canal privado)     |Caixa de correio do usuário         |
|Mensagens de chat em canais padrão e compartilhados    |Caixa de correio associada à equipe pai         |
|Arquivos em canais padrão (por exemplo, conteúdo wiki e arquivos)     |SharePoint site associado à equipe pai        |
|Arquivos em canais privados e compartilhados     |Site SharePoint dedicado associado ao canal
|Conteúdo particular do usuário     |A conta de OneDrive for Business usuário       |
|Conteúdo do cartão em chats|Caixa de correio de usuário para chats 1:1, chats de grupo 1:N e conversas de canal privado; a caixa de correio da equipe pai para conteúdo de cartão em mensagens de canal padrão e compartilhada. Para obter mais informações, consulte a seção "Preservar conteúdo de cartão" em [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Para reter o conteúdo da mensagem em canais privados, você precisa colocar as caixas de correio do usuário (dos membros de um canal privado) em espera. e ao usar a ferramenta Descoberta Eletrônico para pesquisar mensagens de canal privado, você precisa pesquisar a caixa de correio do usuário. Como foi dito anteriormente, os chats de canal privado são armazenados em caixas de correio de usuário, não na caixa de correio de grupo associada à equipe pai.
