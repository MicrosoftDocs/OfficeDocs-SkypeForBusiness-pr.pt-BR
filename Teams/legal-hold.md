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
ms.openlocfilehash: c04f3584aa7207d9d9ee1126df992657f84aa213
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980445"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Colocar um usuário ou uma equipe do Microsoft Teams em retenção legal
==================================================

Quando existe uma expectativa razoável de litígio, é necessário que as organizações preservem as informações armazenadas eletronicamente (ESI), incluindo mensagens de chat do Teams relevantes para o caso. As organizações podem precisar preservar todas as mensagens relacionadas a um tópico específico ou a determinados indivíduos. Este artigo abordará a responsabilidade legal no Microsoft Teams (para lidar com a implementação de responsabilidade em todo o espaço M365, revise Gerenciar casos de Descoberta [Eletrônico:](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Colocar locais de conteúdo em espera.).

> [!NOTE]
> Em fevereiro de 2020, habilitamos a responsabilidade legal ou a espera de casos em canais privados (os chats de canal particular são armazenados em caixas de correio do usuário, os chats de canal normal são armazenados na caixa de correio de um grupo de equipe). Se já houver uma suspensão legal para uma caixa de correio de usuário, a política de suspensão será aplicada automaticamente às mensagens de canal privado armazenadas nessa caixa de correio. Não há mais nenhuma ação necessária para um administrador ativar isso. Também há suporte para a responsabilidade legal dos arquivos compartilhados em canais privados.

No Microsoft Teams, uma equipe inteira ou usuários selecionados podem ser colocados em espera ou em espera legal. Isso garantirá que todas as mensagens trocadas nessas equipes (incluindo canais privados) ou mensagens trocadas por esses indivíduos sejam descobertas pelos gerentes de conformidade da organização ou administradores do Teams.

> [!NOTE]
> A colocação de um usuário em retenção não coloca automaticamente um grupo em retenção ou vice-versa.

Para colocar um usuário ou uma equipe em espera legal:

1. Navegue até o [Centro de Conformidade & segurança.](https://go.microsoft.com/fwlink/?linkid=854628) Quando você cria um caso novo, você se depara com a opção de colocar caixas de correio ou sites em retenção.

2. Vá para a Descoberta Ediscovery ou a Descoberta Avançada e crie um caso clicando em "Criar um caso". Depois que o caso for criado, abra-o.

   > [!div class="mx-imgBorder"]
   > ![A guia Descoberta Online do Microsoft Teams está selecionada, mostrando o botão Criar um caso.](media/LegalHold1.png)

3. Vá para a seção "Retém" no menu superior e clique em "+ Criar" para criar uma espera. Colocar um usuário ou uma equipe em espera salva todas as mensagens trocadas por esses usuários ou mensagens. Quando você cria um caso novo, você se depara com a opção de colocar caixas de correio ou sites em retenção.

   > [!div class="mx-imgBorder"]
   > ![Uma imagem mostrando a guia Retém selecionada e o botão Criar abaixo.](media/LegalHold2.png)

   1. **Nomeia sua hold.** Selecione um nome descritivo e exclusivo para a responsabilidade que você vai criar.

      > [!div class="mx-imgBorder"]
      > ![Esta captura de tela mostra a guia Nome da sua responsabilidade, onde você pode inserir um nome e uma descrição para a responsabilidade que está criando.](media/LegalHold3.png)

    2. **Escolha o local.** Escolha se deseja que a responsabilidade seja aplicada em um usuário ou em uma Equipe inteira (a responsabilidade não pode ser aplicada em canais individuais por enquanto). Observação: se um usuário estiver em espera, todas as suas mensagens estarão em espera, incluindo o que ele enviou em um chat privado, chat entre duas pessoas ou chat em grupo ou uma conversa de canal (incluindo canais privados).
  
       > [!div class="mx-imgBorder"]
       > ![Aqui temos a seção Escolher locais de Criar uma nova responsabilidade, na qual você pode tomar decisões sobre quais opções do M365, incluindo o Microsoft Teams, deseja aplicar a responsabilidade.](media/LegalHold4.png)

    3. **Criar Consulta.** Você pode personalizar a hold se quiser mais granularidade na política de hold. Por exemplo, você pode especificar palavras-chave a serem pesquisadas ou adicionar mais condições, que precisam ser satisfeitas para que a responsabilidade entre em vigor.
    
    4. **Revise suas configurações** antes de publicá-la em sua organização.

Depois que a responsabilidade legal tiver sido definida, você poderá descobrir todo o conteúdo retido por qualquer política de responsabilidade após o artigo de Descoberta [Externa do Teams.](eDiscovery-investigation.md)

> [!IMPORTANT]
> Quando um usuário ou grupo é colocado em espera, todas as cópias da mensagem serão mantidas. Por exemplo, se um usuário postou uma mensagem em um canal e modificou a mensagem, em um cenário de responsabilidade, ambas as cópias da mensagem serão mantidas. Sem a responsabilidade legal in-locar, somente a mensagem mais recente será mantida.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Locais de conteúdo para colocar em espera legal para preservar o conteúdo do Teams

Como um guia útil, você pode usar a tabela a seguir para entender qual local de conteúdo (como uma caixa de correio ou site) colocar em espera legal para preservar diferentes tipos de conteúdo do Teams.

|Cenário  |Local do conteúdo  |
|---------|---------|
|Chats do Teams para um usuário (por exemplo, chats 1:1, chats em grupo 1:N e conversas de canal privado)     |Caixa de correio do usuário.         |
|Chats de canal do Teams (excluindo canais privados)    |Caixa de correio de grupo usada para a equipe.         |
|Conteúdo de arquivo do Teams (por exemplo, conteúdo wiki e arquivos)     |Site do SharePoint usado pela equipe.         |
|Arquivos de canal particular do Teams     |Site dedicado do SharePoint para canais privados.     |
|Conteúdo particular do usuário     |A conta do usuário do OneDrive for Business.         |
|Conteúdo do cartão em chats|Caixa de correio do usuário para chats 1:1, chats em grupo 1:N e conversas de canal privado ou caixa de correio de grupo para conteúdo de cartão em mensagens de canal. Para obter mais informações, consulte a seção "Preservar conteúdo do cartão" em Criar um hold [de Descoberta e.](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> Para manter a comunicação em canais privados, você precisa colocar as caixas de correio do usuário (usuários de canal particular) em espera e, ao usar a ferramenta Descoberta Eletrônico para pesquisar, pesquise na caixa de correio desse usuário. Conforme foi declarado anteriormente, os chats de canal privado são armazenados em caixas de correio do usuário, não na caixa de correio de grupo de uma Equipe.

Se quiser ler mais sobre este tópico para áreas que não são do Teams no Microsoft 365, você deve revisar Gerenciar casos de Descobertas Públicas: Colocar locais de conteúdo em [espera.](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)
