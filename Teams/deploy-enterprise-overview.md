---
title: Visão geral da implantação do Microsoft Teams empresarial
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Saiba como implantar recursos empresariais do Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: fae55eb230c3c0a450a95eb00e50861888bbe3f1
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045570"
---
# <a name="teams-enterprise-deployment-overview"></a>Visão geral da implantação do Microsoft Teams empresarial

Se você for uma empresa de médio ou grande porte, precisará pensar em como implantará o serviço para seus usuários, como implantará o cliente do Microsoft Teams neles, como seu design de rede pode afetar a qualidade da comunicação em tempo real e assim por diante. Confira as seções a seguir para obter indicações de artigos que ajudarão você a planejar o Teams em sua organização.

> [!NOTE]
> Se você ainda não fez isso, é altamente recomendável iniciar a implantação do Teams com um piloto. Um piloto permitirá que você e alguns usuários pioneiros se familiarizem com o Teams e seus recursos antes de planejar e implementar eventualmente. Para obter mais informações sobre como iniciar seu piloto, confira [Introdução ao Microsoft Teams](get-started-with-teams-quick-start.md).

Depois de ler as seções abaixo e estiver pronto para começar a implantar o Teams em sua organização, confira [Configurar o Microsoft Teams em sua empresa](deploy-enterprise-setup.md).

## <a name="architecture"></a>Arquitetura

O Teams está totalmente integrado ao Microsoft 365 e usa muitos recursos para alimentar o chat, compartilhamento de arquivos, reuniões, telefonia, streaming de vídeo e muito mais. Antes de implantar o Teams, confira [Pôsteres de soluções de TI e de soluções de telefonia do Microsoft Teams](teams-architecture-solutions-posters.md) para se familiarizar com como o Teams funciona com o restante do Microsoft 365 para criar uma experiência de colaboração completa para seus usuários.

## <a name="workloads"></a>Cargas de trabalho

O Teams tem três cargas de trabalho que podem ser implantadas independentemente umas das outras **: chats, equipes e canais**; **reuniões e conferências**; e **Sistema de telefonia e Conectividade PSTN (rede telefônica pública comutada)**. Cada carga de trabalho tem sua própria seção em nossa documentação para tornar mais fácil encontrar informações sobre essa carga de trabalho. Isso inclui informações de planejamento de implantação.

Para ver informações de planejamento de implantação para a carga de trabalho que você deseja implantar, confira os seguintes artigos:

- [Chat, equipes e canais](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Reuniões e conferências](deploy-meetings-microsoft-teams-landing-page.md)
- [Sistema de telefonia e Conectividade PSTN](cloud-voice-landing-page.md)

## <a name="network-planner"></a>Planejador de rede

O planejamento de rede para o Teams é extremamente importante quando você tem um grande número de usuários, redes complexas ou ambos. O Teams é compatível com chamadas de voz e videoconferências, que dependem das comunicações em tempo real para proporcionar a melhor experiência possível para os usuários. As redes devem:

- Ter capacidade de largura de banda suficiente para acomodar o número de chamadas de voz simultâneas, videoconferências, reuniões, compartilhamento de tela e assim por diante.
- Ter hardware de rede que dá suporte a protocolos de comunicação em tempo real.
- Permita as portas de rede necessárias entre dispositivos em suas redes, serviços do Microsoft 365 e usuários externos.

Confira os seguintes artigos para ajudá-lo a entender os requisitos de rede do Teams:

- [Preparar a rede da organização para o Microsoft Teams](prepare-network.md)
- [Servidores proxy para Teams ou Skype for Business Online](proxy-servers-for-skype-for-business-online.md)

Para ajudá-lo no planejamento, o Teams inclui o Planejador de Rede. O Planejador de rede pergunta sobre o número e os tipos de usuários que você tem, quantos sites sua organização tem, a capacidade de largura de banda de seus links de rede e muito mais. Usando essas informações, o Planejador de rede cria um relatório que mostra os requisitos de largura de banda para cada atividade, juntamente com as recomendações.

 > [!div class="nextstepaction"]
> [Ir para o Planejador de Rede](https://admin.teams.microsoft.com/networkplanner/organization)

(Você deve ser um [administrador global do Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) para abrir o Planejador de rede.)

Para obter detalhes sobre como o Planejador de rede funciona, consulte [Usar o Planejador de rede para o Microsoft Teams](network-planner.md).

Para ver um exemplo de como o Planejador de rede pode planejar sua rede, consulte [Usando o Planejador de Rede - exemplo de cenário](tutorial-network-planner-example.yml).

## <a name="teams-advisor"></a>Consultor do Teams

O Consultor do Teams é uma solução dentro do Teams que reúne equipes, canais, compartilhamento de arquivos e Planejador, para criar um projeto de implantação para sua organização. O Consultor do Teams cria o plano de projeto, específico para a carga de trabalho selecionada (como chat, equipes e canais), que inclui as tarefas recomendadas que você deve executar durante a implantação. Cada tarefa contém instruções, sugestões e links para artigos relevantes para orientá-lo durante o processo. Você pode facilmente atribuir tarefas a um ou mais indivíduos e especificar datas de início e de término para cada tarefa.

> [!TIP]
> Veja como você pode usar o Consultor do Teams para ajudá-lo a planejar sua implantação do Teams preenchendo [Implementação usando o módulo do Consultor do Teams](/learn/modules/m365-teams-rollout-using-advisor/) no Microsoft Learn.

> [!div class="nextstepaction"]
> [Ir para o Consultor do Teams](https://admin.teams.microsoft.com/teams-deployment)

(Você deve ser um [administrador global do Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) para abrir o consultor do Teams.)

Para obter mais detalhes sobre o funcionamento do Consultor do Teams, consulte [Use o Consultor do Teams para ajudá-lo a implantar o Microsoft Teams](use-advisor-teams-roll-out.md).

## <a name="lifecycle-and-governance-planning"></a>Ciclo de vida e planejamento de governança

Conforme você planeja sua implantação do Teams, é necessário levar em consideração o ciclo de vida de equipes, canais, arquivos e assim por diante em sua organização. Você também deve pensar sobre quais tipos de informações serão armazenadas neles. As equipes podem ser criadas para um projeto específico, para um departamento, ou podem ser usadas como um recurso central para toda a organização. Cada um desses usos tem requisitos diferentes, o que provoca perguntas como as seguintes:

- Por quanto tempo as equipes permanecerão ativas?
- Quem deve ser o titular e gerenciar as equipes e seus canais?
- Determinados requisitos de conformidade devem se aplicar a algumas equipes, mas não a outras?
- Deve haver uma política de nomeação para ajudar os usuários a identificar a equipe certa?

Criar políticas e diretrizes como parte da sua implantação inicial ajudará a garantir que os usuários possam encontrar as informações necessárias. Igualmente importante, no entanto, as políticas apropriadas ajudarão a proteger sua organização contra o vazamento de informações, ajudarão você a se adaptar aos requisitos regulamentadores e a manter as informações conforme necessário para fins de arquivamento.

Para saber mais sobre o gerenciamento do ciclo de vida e a governança no Teams, confira o seguinte:

- [Planejar o gerenciamento do ciclo de vida no Teams](plan-teams-lifecycle.md)
- [Plano de governança no Teams](plan-teams-governance.md)

## <a name="adoption"></a>Adoção

Para garantir que sua organização e seus usuários recebam o máximo do Teams, você precisará de um programa de adoção. Um programa de adoção eficaz pode mobilizar os adotantes antecipados que podem:

- Articular os benefícios do Teams aos colegas e aos líderes de negócios ou de grupo.
- Incentivar outras pessoas que veem como o Teams melhora a colaboração e facilita a conexão entre elas.
- Ajudar a avaliar os processos de negócios existentes e a fazer recomendações sobre como o Teams pode ser integrado a eles.
- Relatar à equipe de implantação tanto sucessos quanto dificuldades para ajudar a melhorar o processo de adoção.

Para obter detalhes sobre como configurar um programa de adoção, consulte [Adote o Microsoft Teams](adopt-microsoft-teams-landing-page.md).