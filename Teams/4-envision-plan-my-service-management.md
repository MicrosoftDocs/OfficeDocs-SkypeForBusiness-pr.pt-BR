---
title: Planejar o gerenciamento do serviço do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Ofereça e mantenha uma implantação de alta qualidade, planejando funções operacionais e atribuindo um defensor de qualidade.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44f68e258535959c164ae838c2c146a4a4b207d9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232290"
---
# <a name="plan-my-service-management"></a>Planejar meu gerenciamento de serviços

Este artigo oferece uma visão geral dos requisitos necessários para oferecer e manter uma implantação de alta qualidade do Microsoft Teams. Você pode ajudar a garantir uma implantação bem-sucedida com o planejamento do gerenciamento e da qualidade do serviço durante a fase de Concepção, antes de fazer o primeiro piloto ou da primeira implantação em produção.

## <a name="service-management-for-teams"></a>Gerenciamento de serviços para o Teams

O gerenciamento do serviço é um tema amplo, que abrange as operações do serviço Microsoft Teams no dia a dia depois que ele é implantado e habilitado para os usuários. O serviço Microsoft Teams abrange o Microsoft Office 365 e os componentes de infraestrutura implantados localmente (por exemplo, a rede).

É provável que a noção de gerenciamento do serviço não seja um conceito novo para a maioria das organizações. Você provavelmente já implementou processos e tarefas que estão associados a serviços existentes. Considerando isso, é possível que você possa expandir o que já está funcionando ao planejar o gerenciamento do serviço atual para dar suporte ao Microsoft Teams no futuro.

O gerenciamento do serviço compreende todas as atividades e processos envolvidos no gerenciamento do Microsoft Teams de ponta a ponta. Alguns componentes do gerenciamento de serviços (os componentes de infraestrutura que o próprio serviço do Office 365 abrange) são de responsabilidade da Microsoft, ao passo que o cliente é responsável por gerenciar os diversos aspectos do Teams, a rede e os pontos de extremidade que fornecem.
Para ver uma discussão completa sobre a responsabilidade do cliente pelo gerenciamento de serviços do Teams e como ele se relaciona com os principais componentes que sustentam a qualidade da experiência do usuário, consulte [Planejar gerenciamento de serviços e qualidade](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide).

![Diagrama dos três componentes de qualidade] (media/plan-my-service-management-image1.png "Diagrama dos três componentes de qualidade--serviço do Office 365, rede e pontos de extremidade--e como o gerenciamento de serviços se sobrepõe a todos os três.")

<!--ENDOFSECTION-->

## <a name="introduction-to-the-operations-guide"></a>Introdução ao Guia de Operações 

**O que**, **quem** e **como** são três perguntas importantes que precisam ser respondidas ao lidar com o gerenciamento do serviço.

O [Guia de Operações](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) pode ajudar a responder a essas três perguntas. O guia fornece uma lista de atividades que devem ser realizadas diariamente, semanalmente, mensalmente e conforme a necessidade. Essas atividades e tarefas são essenciais para a manutenção de uma implantação do Microsoft Teams de alta qualidade. A determinação de quem será responsável pela realização de atividades específicas de gerenciamento do serviço é um aspecto crítico do planejamento que você precisa fazer logo no início da fase de Concepção para garantir o sucesso da implantação. Depois que você identificar essas tarefas e atividades, os grupos ou as pessoas aos quais elas serão atribuídas deverão entendê-las e acompanhá-las. O Guia de Operações apresenta informações e orientações para a realização de cada uma das tarefas e/ou referências de conteúdo externo.

## <a name="plan-for-operational-role-mapping"></a>Plano de mapeamento de funções operacionais

O planejamento inicial do gerenciamento do serviço é uma etapa crítica, pois a fase de operações começa quando os primeiros usuários piloto são habilitados. A equipe do projeto deve revisar e concordar com as tarefas e atividades necessárias, identificar a equipe que será responsável por cada tarefa operacional e então obter o comprometimento e a aprovação de cada equipe envolvida.

Após a conclusão da aprovação, a equipe responsável deve iniciar a operacionalização das funções e responsabilidades. Isso pode incluir um processo de treinamento e preparação, a atualização do modelo de alocamento de pessoal ou a verificação de que os parceiros externos estão prontos para o fornecimento.

O mapeamento de funções operacionais no início da fase de Concepção permite que todas as equipes iniciem suas tarefas operacionais durante as operações piloto e de preparação, e garantam que tudo esteja pronto após o início da implantação.

O Guia de Operações apresenta uma lista de tarefas comuns mapeadas para as funções típicas que devem ser válidas na maioria dos cenários. Você precisa personalizar essas responsabilidades de maneira adequada para a sua organização.

>[!TIP]
>Segue um exemplo de um modelo para documentar o resultado do exercício de mapeamento de funções operacionais que você realizou para dar suporte a esse projeto.


|Função operacional |Descrição |Equipe |Detalhes de contato |
|---------|---------|---------|---------|
|Proprietário do serviço|Proprietário do serviço, interface com as divisões da empresa, estratégia|TBA|TBA|
|Operações de Audioconferência|Operações diárias, migração/adição/alteração de contas de usuários e dispositivos, monitoramento|TBA| TBA| 
|Administração de locatários|Alterar configuração de todos os locatários, habilitar novos recursos|TBA|TBA|
|Central de atendimento|Interface para os usuários obterem suporte|TBA|TBA|
|Operações de rede|Executar LAN, WAN, Wi-Fi e acesso à internet|TBA|TBA|
|Cliente e equipe de pontos de extremidade|Gerenciar implantações de desktop|TBA|TBA|
|Operações de identidade|Gerenciar infraestrutura de identidade (Active Directory, Serviços de Federação do Active Directory, Azure AD)|TBA|TBA|
|Gerenciamento de mudanças/adoção|Gerenciar conscientização, treinamentos e adoção da solução|TBA|TBA|
|Operações do Exchange|Gerenciar o ambiente do Exchange|TBA|TBA|
|Operações de telefonia|Gerenciar os SBCs e os números de telefone|TBA|TBA|

<!--ENDOFSECTION-->

## <a name="the-quality-champion-role"></a>Função de defensor da qualidade

Todos os grupos ou indivíduos precisam se responsabilizar pela qualidade em todas as organizações.
Essa é a função mais importante do gerenciamento do serviço. O especialista em qualidade é uma função de cliente atribuída a uma pessoa ou grupo que é apaixonado pela experiência dos usuários. Essa função requer a habilidade de identificar tendências no ambiente e a capacidade de trabalhar com outras equipes para possibilitar correções.
O melhor candidato para a Quality Champion geralmente é o proprietário do atendimento ao cliente, quem, dependendo do tamanho e da complexidade da organização, pode ser qualquer pessoa ou grupo que seja apaixonado pela experiência do usuário.

O especialista em qualidade aproveita as ferramentas existentes e os processos documentados, como o painel de qualidade de chamada (CQD) e o guia de avaliação da experiência de qualidade, para monitorar a experiência do usuário, identificar tendências de qualidade e remediação quando necessário. O especialista em qualidade funciona com as respectivas equipes para direcionar as ações de correção, gerando relatórios para um Comitê de direcionamento sobre seus problemas de progresso e abertura.

As tarefas e atividades associadas à função são documentadas no guia de operações. Essa função deve ser atribuída logo no início da fase de Concepção. Um etapa importante da operacionalização da função de defensor da qualidade é a obtenção do conhecimento necessário para a função e a garantia de que os pré-requisitos para a execução das tarefas foram cumpridos. Uma tarefa importante dessa função é a realização periódica de uma revisão da experiência de qualidade.

<!--ENDOFSECTION-->

## <a name="introduction-to-the-quality-experience-review-guide"></a>Introdução ao Guia de Revisão da Experiência de Qualidade

O guia de avaliação da experiência de qualidade tem um conjunto de atividades que avaliam e fornecem orientação de correção em áreas importantes que têm o maior impacto para melhorar a experiência do usuário, conforme mostrado na figura abaixo.

![Ilustração de áreas importantes para examinar durante a análise da experiência de qualidade] (media/plan-my-service-management-image2.png "As principais áreas a serem examinadas durante uma revisão da experiência de qualidade: áudio, confiabilidade e resultados da pesquisa de usuários.")

Por meio da avaliação e correção contínuas das áreas descritas neste documento, você pode reduzir seu potencial de afetar negativamente a experiência do usuário. A maioria dos problemas de experiência do usuário encontrada em uma implantação pode ser agrupada nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy

-   Cobertura insatisfatória da rede Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Uso de dispositivos de áudio internos ou não otimizados

-   Dispositivos de rede ou sub-redes com problemas

As orientações fornecidas no Guia de Revisão da Experiência de Qualidade concentram-se no uso do Painel de Qualidade de Chamadas (PQC) Online como ferramenta principal para relatar e investigar cada área descrita, com foco sobre o áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

É altamente recomendável que você innomeado o especialista em qualidade no início. Depois de serem nomeados, eles devem começar a se familiarizar com o conteúdo do [Guia de revisão de experiência de qualidade](https://aka.ms/qerguide).



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decidir quem é responsável pelas operações de voz em nuvem em sua organização.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Baixe o guia planejamento para o gerenciamento de serviços completo.</li><li>Baixe o guia de avaliação da experiência de qualidade.</li><li>Examine o guia de operações totalmente.</li><li>Fornecer todos os guias para que todos os membros da equipe de operações possam revisar e se familiarizar com os requisitos de operações.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->