---
title: Use o assistente de integração do Trabalhadores de Linha de Frente para que sua força de trabalho na linha de frente entre em funcionamento
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o assistente de integração do Trabalho de Linha de Frente para implantar rapidamente uma experiência no Teams que é personalizada para os funcionários e gerentes de linha de frente em sua organização.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97f8994ecc5c7aef610e040f30b43803f03c6844
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2022
ms.locfileid: "61993187"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Use o assistente de integração do Trabalhadores de Linha de Frente para que sua força de trabalho na linha de frente entre em funcionamento

## <a name="overview"></a>Visão Geral

O assistente de integração do Trabalhador de Linha de Frente no Centro de administração do Microsoft 365 simplifica a integração de funcionários de linha de frente para sua organização. O assistente permite implantar rapidamente uma experiência no Microsoft Teams que é personalizada para sua força de trabalho de linha de frente. Usando o assistente, você pode facilmente começar sua implantação piloto de Teams para os funcionários de linha de frente em sua organização.

O assistente configura uma equipe para seus funcionários de linha de frente e atribui licenças e pacotes de [política](manage-policy-packages.md) a cada membro da equipe. Você pode criar sua equipe do zero ou de um modelo [de](get-started-with-teams-templates-in-the-admin-console.md) equipe e, em seguida, adicionar usuários e atribuir funções. A função determina o pacote de política que o assistente atribui a cada usuário.

Atualmente, o assistente dá suporte à adição de 100 usuários sempre que você o executar. Estamos trabalhando para aumentar o número de usuários por executar em breve. Confira aqui as atualizações mais recentes.

O assistente está disponível para todas as organizações que tenham pelo menos uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline). Você pode executar o assistente quantas vezes precisar para Teams sua força de trabalho de linha de frente em locais ou sites diferentes em toda a sua organização.

Confira este breve vídeo para ver uma visão geral de como executar o assistente para integrar sua força de trabalho de linha de frente.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> Esse assistente permite que você aborde rapidamente sua força de trabalho de linha de frente Teams através do Centro de administração do Microsoft 365. Para obter informações sobre como implantar Teams à força de trabalho de linha de frente usando scripts, consulte [How to provision Teams at scale for Frontline Workers](flw-scripted-deployment.md).

> [!NOTE]
> O assistente ainda não dá suporte a [rótulos de sensibilidade](sensitivity-labels.md) . Se sua organização exigir rótulos de sensibilidade para criar uma equipe, você não verá o assistente no Centro de administração do Microsoft 365.

## <a name="run-the-wizard"></a>Executar o assistente

1. Na navegação à [esquerda do Centro de administração do Microsoft 365](https://admin.microsoft.com/), escolha **Instalação**. Vá para a seção **Aplicativos e email** e, em **Seguida**, em Obter sua força de trabalho de linha de frente funcionando, selecione **Exibir**. Aqui, você pode saber mais sobre os recursos que Microsoft 365 profissionais de linha de frente oferece.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Captura de tela da página de detalhes da experiência de integração do Trabalho de Linha de Frente no Centro de administração do Microsoft 365" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. Quando estiver pronto, selecione **Começar a** executar o assistente.

3. Insira um nome para sua equipe, adicione um ou mais proprietários de equipe e selecione uma configuração de privacidade. Em seguida, escolha se deve criar sua equipe do zero ou de um modelo de equipe. Os modelos de equipe vêm com canais e guias predefinidos, que otimizam a equipe para uma determinada necessidade de negócios ou projeto.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="Captura de tela da página Configurar uma equipe do assistente" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. Adicione usuários à equipe. Você também pode adicionar grupos. Se você adicionar grupos, lembre-se de que licenças e pacotes de política são atribuídos diretamente a cada usuário no grupo, não ao grupo em si.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="Captura de tela da página Adicionar usuários do assistente em que você adiciona usuários e grupos à sua equipe" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. Atribua uma das seguintes funções a cada membro da equipe: Frontline Worker, Frontline Manager, None. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="Captura de tela da página Atribuir funções de trabalho do assistente em que você atribui funções, locais e licenças aos membros da equipe" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    Ao atribuir uma função de Gerente de Linha de Frente ou Trabalhador de Linha de Frente, esse usuário receberá um pacote de política. O pacote de política criará uma experiência em Teams que é adaptada à sua função. Essa experiência inclui aplicativos e políticas pré-fixados para comunicação e colaboração de funcionários e gerentes de linha de frente saudáveis.

    Em seguida, selecione um local e atribua uma Microsoft 365 F a cada membro da equipe. Se você não tiver licenças suficientes, poderá selecionar **Comprar mais licenças** para comprar mais licenças.  

6. Escolha quem recebe o email de status após a conclusão do assistente. O email contém informações de sucesso e falha sobre as ações executadas pelo assistentecriando&mdash; a equipe, adicionando membros da equipe e atribuindo uma licença e um pacote de política a cada membro da equipe. Use essas informações para solucionar erros que possam ocorrer.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="Captura de tela da página Adicionar destinatários de email de status do assistente" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. Revise suas seleções e selecione **Confirmar**.

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="Captura de tela da página Revisar equipe do assistente em que você analisa as configurações da equipe" lightbox="media/flw-onboarding-wizard-review-team.png":::

    O assistente cria sua equipe e atribui licenças e pacotes de política aos membros da equipe. Pode levar alguns minutos para ser concluído, após o qual os destinatários escolhidos receberão um email de status.

8. Você está a caminho, mas ainda não terminou! Em seguida, confira a [seção O que fazer depois de executar a seção assistente](#what-to-do-after-running-the-wizard) deste artigo.

## <a name="what-to-do-after-running-the-wizard"></a>O que fazer depois de executar o assistente

Depois de executar o assistente, é importante:

- Deixe seus funcionários e gerentes de linha de frente saberem que eles são atribuídos Teams licenças.
- Se você estiver usando dispositivos compartilhados, certifique-se de Teams esteja instalado nesses dispositivos. Se sua organização usa um modelo de "traga seu próprio dispositivo", deixe seus funcionários e gerentes de linha de frente saberem que eles precisam baixar e instalar Teams em seus dispositivos.

Quando o funcionário da linha de frente abrir o Teams pela primeira vez, ele receberá uma experiência de primeira executar personalizada, que inclui chats e canais, chamada e gerenciamento de tarefas em todos os Teams.

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar pacotes de política em equipes](manage-policy-packages.md)
- [Usar modelos de equipe no Teams de administração](get-started-with-teams-templates-in-the-admin-console.md)
