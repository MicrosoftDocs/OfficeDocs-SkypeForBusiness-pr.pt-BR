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
description: Saiba como colocar um usuário ou uma equipe do Microsoft Teams em retenção legal usando o Centro de Segurança e Conformidade, e saiba o que necessita de uma retenção legal com base nas exigências de dados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ace4098b56539408e8c29e5d16e43c8ae255f372
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013345"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Colocar um usuário ou uma equipe do Microsoft Teams em retenção legal

Quando existe uma expectativa razoável de litígio, as organizações são obrigadas a preservar as informações armazenadas eletronicamente (ESI), incluindo as mensagens de chat do Teams que são relevantes para o caso. As organizações podem precisar preservar todas as mensagens relacionadas a um tópico específico ou a determinados indivíduos. Este artigo abrange a ressarção legal no Microsoft Teams. Para manter o conteúdo no Microsoft 365, consulte [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> Em fevereiro de 2020, acariámos a responsabilidade legal para canais privados. Chats de canal privado são armazenados em caixas de correio de usuário, enquanto chats de canal normal são armazenados na caixa de correio de grupo do Teams. Se já houver uma suspensão legal para uma caixa de correio de usuário, a política de espera será aplicada automaticamente às mensagens de canal privado armazenadas nessa caixa de correio. Não há mais nenhuma ação necessária para um administrador ativar isso. Também há suporte para a responsabilidade legal dos arquivos compartilhados em canais privados.

No Microsoft Teams, uma equipe inteira ou usuários selecionados podem ser colocados em espera legal. Isso garantirá que todas as mensagens que foram trocadas nessas equipes (incluindo canais privados) ou mensagens trocadas por essas pessoas sejam descobertas pelos gerentes de conformidade da organização ou administradores do Teams.

> [!NOTE]
> A colocação de um usuário em retenção não coloca automaticamente um grupo em retenção ou vice-versa.
> As notificações enviadas no feed de atividade não podem ser colocadas em espera.

Para colocar um usuário ou uma equipe em uma responsabilidade legal em um caso de Descoberta Interna Principal:

1. Vá para o centro de conformidade do [Microsoft 365.](https://compliance.microsoft.com) Quando você cria um caso novo, você se depara com a opção de colocar caixas de correio ou sites em retenção.

2. Vá para **eDiscovery**  >  **Core** e crie uma ocorrência clicando em **Criar um caso**. Depois que o caso for criado, abra-o.
  
   ![A guia Descoberta Online do Microsoft Teams está selecionada, mostrando o botão Criar uma ocorrência.](media/LegalHold1.png)

   > [!NOTE]
   > Você também pode colocar um usuário em uma responsabilidade associada a um caso de Descoberta Avançada. Para obter mais informações, consulte [Manage holds in Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Vá até a guia **Retém** no menu superior e clique **em Criar** para criar uma espera. Colocar um usuário ou uma equipe em espera preserva todas as mensagens trocadas por esses usuários ou mensagens. Quando você cria um caso novo, você se depara com a opção de colocar caixas de correio ou sites em retenção.

   ![Uma imagem mostrando a guia Retém selecionada e o botão Criar abaixo.](media/LegalHold2.png)
    
    1. **Nomeia sua espera**. Selecione um nome descritivo e exclusivo para a espera que você vai criar.
  
       ![Esta captura de tela mostra a guia Nome da sua espera, onde você pode inserir um nome e uma descrição para a bloqueio que você está criando.](media/LegalHold3.png)

    1. **Escolha local**. Escolha se deseja que a responsabilidade seja aplicada em um usuário ou em uma Equipe inteira (a espera não pode ser aplicada em canais individuais por enquanto). Observação: se um usuário estiver em espera, todas as mensagens estarão em espera, incluindo o que enviou em um chat 1:1, 1:1 ou chat em grupo ou uma conversa de canal (incluindo canais privados).
    ![Aqui temos a seção Escolher locais de Criar uma nova responsabilidade, onde você pode tomar decisões sobre quais opções do M365, incluindo o Microsoft Teams, deseja que a responsabilidade seja aplicada.](media/LegalHold4.png)

    2. **Criar consulta**. Você pode personalizar a espera se quiser mais granularidade na política de espera. Por exemplo, você pode especificar palavras-chave a serem pesquisadas, ou você pode adicionar mais condições, que precisariam ser atendidas para que a espera entre em vigor.
    
    3. **Revise suas configurações antes** de criar a espera.

Depois que a responsabilidade legal tiver sido criada, você poderá pesquisar o conteúdo mantido por qualquer política de responsabilidade. Para obter mais informações, [consulte Conduct an eDiscovery investigation in Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Quando um usuário ou grupo é colocado em espera, todas as cópias de mensagem serão mantidas. Por exemplo, se um usuário postou uma mensagem em um canal e modificou a mensagem, em um cenário de espera, ambas as cópias da mensagem serão mantidas. Sem a responsabilidade legal in-locar, somente a mensagem mais recente será mantida.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Locais de conteúdo para colocar em espera legal para preservar o conteúdo do Teams

Como um guia útil, você pode usar a tabela a seguir para entender qual local de conteúdo (como uma caixa de correio ou site) colocar em espera legal para preservar diferentes tipos de conteúdo do Teams.

|Cenário  |Local do conteúdo  |
|---------|---------|
|Chats do Teams para um usuário (por exemplo, chats 1:1, chats de grupo 1:N e conversas de canal privado)     |Caixa de correio do usuário.         |
|Chats de canal do Teams (excluindo canais privados)    |Caixa de correio de grupo usada para a equipe.         |
|Conteúdo de arquivo do Teams (por exemplo, conteúdo wiki e arquivos)     |Site do SharePoint usado pela equipe.         |
|Arquivos de canal privado do Teams     |Site dedicado do SharePoint para canais privados.     |
|Conteúdo particular do usuário     |A conta do OneDrive for Business do usuário.         |
|Conteúdo do cartão em chats|Caixa de correio de usuário para chats 1:1, chats de grupo 1:N e conversas de canal privado ou caixa de correio de grupo para conteúdo de cartão em mensagens de canal. Para obter mais informações, consulte a seção "Preservar conteúdo de cartão" em [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|


> [!NOTE]
> Para manter a comunicação em canais privados, você precisa colocar as caixas de correio do usuário ( usuários de canal privado) em espera e, ao usar a ferramenta de Descoberta Eletrônico para pesquisar, você deve pesquisar na caixa de correio desse usuário. Como foi dito anteriormente, os chats de canal privado são armazenados em caixas de correio de usuário, não na caixa de correio de grupo de uma Equipe.

Se você quiser ler mais sobre este tópico para áreas que não são do Teams no Microsoft 365, revise Gerenciar casos de Descoberta e: Colocar locais de conteúdo [em espera.](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)
