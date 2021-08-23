---
title: Use o assistente de integração do Trabalho de Linha de Frente para fazer sua força de trabalho de linha de frente funcionar
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o assistente de integração do Trabalho de Linha de Frente para implantar rapidamente uma experiência no Teams que é personalizada para os funcionários e gerentes de linha de frente em sua organização.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 461e73a4c4008d028e564c25b5842c7b59e2a57b
ms.sourcegitcommit: b17e5acadcca0261eaccc64e1b4ee457348f975c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2021
ms.locfileid: "58365910"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Use o assistente de integração do Trabalho de Linha de Frente para fazer sua força de trabalho de linha de frente funcionar

> [!NOTE]
> Este artigo descreve um recurso que ainda não foi lançado. Ele está chegando em breve. Se você for um administrador, poderá descobrir quando esse recurso será lançado no Centro de Mensagens (no Centro de administração do Microsoft 365 [).](https://portal.office.com/adminportal/home) Para ficar por dentro dos recursos Teams futuros, confira [o roteiro Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Visão Geral

O assistente de integração do Trabalhador de Linha de Frente no Centro de administração do Microsoft 365 simplifica a integração de funcionários de linha de frente para sua organização. O assistente permite implantar rapidamente uma experiência no Microsoft Teams que é personalizada para sua força de trabalho de linha de frente. Usando o assistente, você pode facilmente começar sua implantação piloto de Teams para os funcionários de linha de frente em sua organização.

O assistente configura uma equipe para seus funcionários de linha de frente e atribui licenças e pacotes de [política](manage-policy-packages.md) a cada membro da equipe. Você pode criar sua equipe do zero ou de um modelo [de equipe](get-started-with-teams-templates-in-the-admin-console.md)e, em seguida, adicionar usuários e atribuir funções. A função determina o pacote de política que o assistente atribui a cada usuário.

O assistente está disponível para todas as organizações que tenham pelo menos uma Microsoft 365 F. Você pode executar o assistente quantas vezes precisar para Teams sua força de trabalho de linha de frente em locais ou sites diferentes em toda a sua organização.

> [!NOTE]
> Esse assistente permite que você aborde rapidamente seus funcionários de linha de frente Teams pelo Centro de administração do Microsoft 365. Para obter mais informações sobre como implantar Teams seus funcionários de linha de frente usando scripts, consulte How to provision [Teams at scale for Frontline Workers](flw-scripted-deployment.md).

## <a name="run-the-wizard"></a>Executar o assistente

1. Na navegação à esquerda [do](https://admin.microsoft.com/)Centro de administração do Microsoft 365, selecione **Configurar**. Vá para a seção **Aplicativos e email** e, em **Seguida,** em Obter sua força de trabalho de linha de frente funcionando , selecione **Exibir**. Aqui, você pode saber mais sobre os recursos que Microsoft 365 profissionais de linha de frente oferece.

2. Quando estiver pronto, selecione **Começar a** executar o assistente.

3. Insira um nome para sua equipe, selecione uma configuração de privacidade e adicione um ou mais proprietários de equipe. Em seguida, escolha se deve criar sua equipe do zero ou de um modelo de equipe. Os modelos de equipe vêm com canais e guias predefinidos, que otimizam a equipe para uma determinada necessidade de negócios ou projeto.

4. Adicione usuários à equipe. Você também pode adicionar grupos. Se você adicionar grupos, lembre-se de que licenças e pacotes de política são atribuídos diretamente a cada usuário no grupo, não ao grupo em si.

5. Atribua uma das seguintes funções a cada membro da equipe.

    - Trabalhador de linha de frente
    - Gerenciador de frontline
    - Nenhum

    Ao atribuir uma função de gerente de linha de frente ou de linha de frente, esse usuário receberá uma experiência Teams que é adaptada à sua função. Isso inclui aplicativos e políticas pré-fixados para comunicação e colaboração de funcionários e gerentes de linha de frente saudáveis.

    Em seguida, atribua uma Microsoft 365 F a cada membro da equipe. Se você não tiver licenças suficientes, poderá selecionar **Comprar mais licenças** para comprar mais licenças.  

6. Escolha quem recebe o email de status após a conclusão do assistente. O email contém informações de sucesso e falha sobre as ações executadas pelo assistente criando a equipe, adicionando membros da equipe e atribuindo uma licença e um pacote de política a cada membro &mdash; da equipe. Use essas informações para solucionar erros que possam ocorrer.

7. Revise suas seleções e selecione **Confirmar**.

    O assistente cria sua equipe e atribui licenças e pacotes de política aos membros da equipe. Isso pode levar alguns minutos para ser concluído, após o qual os destinatários escolhidos receberão um email de status.

8. Você está a caminho, mas ainda não terminou! Em seguida, confira a [seção O que fazer depois](#what-to-do-after-running-the-wizard) de executar a seção assistente deste artigo.

## <a name="what-to-do-after-running-the-wizard"></a>O que fazer depois de executar o assistente

Depois de executar o assistente, é importante:

- Deixe seus funcionários e gerentes de linha de frente saberem que eles são atribuídos Teams licenças.
- Se você estiver usando dispositivos compartilhados, certifique-se de Teams esteja instalado nesses dispositivos. Se sua organização usa um modelo de "traga seu próprio dispositivo", deixe seus funcionários e gerentes de linha de frente saberem que eles precisam baixar e instalar Teams em seus dispositivos.

Quando o funcionário da linha de frente abrir o Teams pela primeira vez, ele receberá uma experiência de primeira executar personalizada, que inclui chats e canais, chamada e gerenciamento de tarefas em todos os Teams.

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar pacotes de política em equipes](manage-policy-packages.md)
- [Usar modelos de equipe no Teams de administração](get-started-with-teams-templates-in-the-admin-console.md)