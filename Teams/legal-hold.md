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
description: Saiba como colocar um usuário Microsoft Teams equipe em retenção legal usando o portal de conformidade do Microsoft Purview e aprender o que precisa de uma retenção legal com base nos requisitos de dados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d56bece07fe7342c4156abdae73508a1a149864
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922452"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Colocar um usuário ou uma equipe do Microsoft Teams em retenção legal

Quando existe uma expectativa razoável de litígio, as organizações precisam preservar as ESI (informações armazenadas eletronicamente), incluindo Teams mensagens de chat relevantes para o caso. As organizações podem precisar preservar todas as mensagens relacionadas a uma investigação específica ou a uma pessoa específica. Este artigo abordará o uso de uma retenção legal para preservar o conteúdo Microsoft Teams. Para preservar o conteúdo em outros serviços Microsoft 365, consulte Criar uma retenção [de Descoberta Eletrônica](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> Em fevereiro de 2020, habilitamos a retenção legal para canais privados. Chats de canal privado são armazenados em caixas de correio do usuário, enquanto chats de canal padrão são armazenados na caixa de correio associada à equipe pai. Se já houver uma retenção legal em vigor para uma caixa de correio de usuário, a política de retenção agora será aplicada automaticamente às mensagens de canal privado armazenadas nessa caixa de correio. Não há nenhuma ação adicional necessária para um administrador ativar isso. Também há suporte para a retenção legal de arquivos compartilhados em canais privados.

Dentro Microsoft Teams, uma equipe inteira ou usuários selecionados podem ser colocados em retenção legal. Isso garantirá que todas as mensagens trocadas nessas equipes (incluindo canais privados e compartilhados) ou mensagens trocadas por essas pessoas sejam detectáveis pelos gerentes de conformidade ou administradores do Teams da organização.

> [!NOTE]
> A colocação de um usuário em retenção não coloca automaticamente um grupo em retenção ou vice-versa.
> As notificações enviadas nos feeds de atividades não podem ser colocadas em espera.

Para colocar um usuário ou uma equipe em retenção legal em um caso de Descoberta Eletrônica Principal:

1. Acesse o [portal de conformidade do Microsoft Purview](https://compliance.microsoft.com). Ao criar um novo caso, você verá a opção de colocar caixas de correio ou sites em espera.

2. Vá para **eDiscoveryCore** >  **e** crie um caso clicando em **Criar um caso**. Depois que o caso for criado, abra-o.
  
   ![Microsoft Teams guia Descoberta Eletrônica está selecionada, mostrando o botão Criar um caso.](media/LegalHold1.png)

   > [!NOTE]
   > Você também pode colocar um usuário em uma retenção associada a um Advanced eDiscovery caso. Para obter mais informações, consulte [Gerenciar retenções Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Vá para a **guia** Retenções no menu superior e clique **em Criar** para criar uma retenção. Colocar um usuário ou uma equipe em espera preserva todas as mensagens trocadas por esses usuários. Ao criar um novo caso, você verá a opção de colocar caixas de correio ou sites em espera.

   ![Uma imagem mostrando a guia Retenções selecionada e o botão Criar abaixo.](media/LegalHold2.png)

   1. **Nomeie sua suspensão**. Selecione um nome descritivo e exclusivo para a retenção que você criará.
  
       ![Esta captura de tela mostra a guia Nomear sua retenção, na qual você pode inserir um nome e uma descrição para a retenção que você está criando.](media/LegalHold3.png)

   2. **Escolha o local**. Escolha se deseja que a retenção seja aplicada em um usuário ou em uma equipe inteira (uma retenção não pode ser aplicada em canais individuais por enquanto). Se um usuário estiver em espera, todas as mensagens serão preservadas, incluindo mensagens em chats 1:1, chats em grupo e canais privados. As mensagens em canais padrão e compartilhados são preservadas quando a equipe pai é colocada em espera.

      ![Escolha os locais de dados que você deseja colocar em espera.](media/LegalHold4.png)

   3. **Criar consulta**. Você pode personalizar a retenção se quiser mais granularidade na política de retenção. Por exemplo, você pode especificar palavras-chave a serem pesquisadas ou adicionar mais condições, que precisariam ser atendidas para que a retenção entre em vigor.

   4. **Examine suas configurações antes** de criar a retenção.

Depois que a retenção for criada, você poderá pesquisar o conteúdo retido pela política de retenção. Para obter mais informações, [consulte Realizar uma investigação de](eDiscovery-investigation.md) Descoberta Eletrônica Teams.

> [!IMPORTANT]
> Quando um usuário ou grupo é colocado em espera, todas as cópias de conformidade das mensagens são preservadas. Por exemplo, se um usuário postar uma mensagem em um canal e, em seguida, modificar a mensagem, ambas as cópias da mensagem serão preservadas. Sem a retenção, somente a mensagem mais recente é preservada.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Locais de conteúdo a serem mantidos em espera para preservar Teams conteúdo

Como um guia útil, use a tabela a seguir para entender quais locais de conteúdo (como uma caixa de correio ou um site) colocar em espera para preservar diferentes tipos de Teams conteúdo.

|Cenário  |Local do conteúdo  |
|---------|---------|
|Mensagens de chat para um usuário (por exemplo, chats 1:1, chats em grupo 1:N e conversas de canal privado)     |Caixa de correio do usuário         |
|Mensagens de chat em canais padrão e compartilhados    |Caixa de correio associada à equipe pai         |
|Arquivos em canais padrão (por exemplo, conteúdo e arquivos wiki)     |SharePoint site associado à equipe pai        |
|Arquivos em canais privados e compartilhados     |Site SharePoint dedicado associado ao canal
|Conteúdo privado do usuário     |A conta de OneDrive for Business usuário       |
|Conteúdo do cartão em chats|Caixa de correio do usuário para chats 1:1, chats em grupo 1:N e conversas de canal privado; a caixa de correio da equipe pai para conteúdo do cartão em mensagens de canal padrão e compartilhadas. Para obter mais informações, consulte a seção "Preservar conteúdo do cartão" em [Criar uma retenção de Descoberta Eletrônica](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Para manter o conteúdo da mensagem em canais privados, você precisa colocar as caixas de correio do usuário (dos membros de um canal privado) em espera. e ao usar a ferramenta descoberta eletrônica para pesquisar mensagens de canal privado, você precisa pesquisar a caixa de correio do usuário. Como foi dito anteriormente, os chats de canal privado são armazenados em caixas de correio do usuário, não na caixa de correio do grupo associada à equipe pai.
