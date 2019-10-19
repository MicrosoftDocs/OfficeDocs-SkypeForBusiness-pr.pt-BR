---
title: Planejar reuniões grandes no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumo: Leia este tópico para saber mais sobre as práticas recomendadas para implementar e gerenciar reuniões grandes no Skype for Business Server.'
ms.openlocfilehash: 136896a45be36508af419d84bc5bd684c9d8a429
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "34696040"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planejar reuniões grandes no Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre as práticas recomendadas de implementação e gerenciamento de reuniões grandes no Skype for Business Server.
  
O tamanho das reuniões que o Skype for Business Server pode suportar depende se a conferência está hospedada em um pool compartilhado ou dedicado: em qualquer lugar da 250 participantes em um pool compartilhado para 1000 participantes em um pool dedicado. 
  
> [!NOTE]
> Este tópico se concentra em práticas recomendadas para reuniões grandes com suporte no Skype for Business Server. Se a sua organização requer recursos de reunião maiores, você deve considerar a implementação de um ambiente híbrido que aproveita a transmissão de reunião do Skype, um novo serviço online que faz parte do Office 365. 

> [!NOTE]
> A Transmissão de Reunião do Skype habilita os usuários a hospedarem e divulgarem a grandes públicos online reuniões com até 10.000 participantes. O uso de Transmissão de Reunião do Skype exige que o Skype for Business Server esteja configurado como híbrido em um locatário do Office 365 de produção. Todos os usuários devem estabelecer um locatário online, isso é um pré-requisito. Se você estiver interessado em implantar uma solução híbrida que possa tirar proveito da transmissão de reunião do Skype, confira [o que é uma transmissão de reunião do Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) e [configure sua implantação local para a transmissão de reunião do Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
Grandes reuniões costumam ter as seguintes características:
  
- O formato da reunião é uma apresentação de um-para-muitos.
    
- Um ou alguns usuários são representados e todos eles participam somente como participantes.
    
- O compartilhamento de apresentação do PowerPoint é a principal atividade de colaboração de dados.
    
- O áudio é exigido e o vídeo também pode ser utilizado.
    
- Uma pessoa dedicada, geralmente o organizador da reunião ou um assistente do organizador, configura a reunião com antecedência.
    
- Uma equipe dedicada (não os apresentadores) conduz a reunião, incluindo estabelecer uma conexão para uma reunião online, verificar se o áudio, vídeo e compartilhamento de slides estão funcionando, gerenciar lobby e funções dos usuários, ligar e desligar o microfone dos participantes, responder perguntas e gerenciar gravações, conforme apropriado.
    
Quando um usuário agenda uma reunião, o Skype for Business Server cria um registro no banco de dados de conferência, que armazena dados de conferência, mas não reserva nenhum recurso de hardware para a reunião agendada antes do tempo. Em vez disso, o Skype for Business Server tem lógica de balanceamento de carga interna para alocar dinamicamente recursos de conferência em servidores front-end, de forma que distribua cargas igualmente em todos os servidores de front-end do pool. Isso provisiona e usa com eficiência os recursos de hardware, mas é importante que você planeje adequadamente o suporte para reuniões muito grandes. 
  
Por exemplo, quando um pool do Skype for Business Server está ficando próximo à sua capacidade máxima, cada servidor front-end pode hospedar aproximadamente 125 reuniões de tamanho médio. Adicionar outra reunião pequena não seria problema, mas adicionar uma reunião para 1.000 usuários, sim, pois os Servidores Front-End provavelmente não seriam compatíveis com tal reunião grande ao mesmo tempo que as outras 125 reuniões.
  
O suporte a grandes reuniões de até 1.000 participantes exige lidar com os problemas relacionados tanto ao modelo de hardware compartilhado quanto ao modelo sem reserva. Em geral, você precisa planejar um pool dedicado e seguir as práticas recomendadas, conforme descrito nas seções a seguir. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planeje um pool dedicado

Se a sua organização requer reuniões com mais de 250 participantes, será necessário planejar um pool dedicado para suportar a carga. 
  
Para ter recursos de CPU e memória suficientes para as reuniões com até 1.000 usuários, os Servidores Front-End de hospedagem não devem hospedar nenhuma outra carga de trabalho de mensagens instantâneas (IM) e presença nem do Enterprise Voice. Os servidores também não devem hospedar nenhuma outra reunião, independente do tamanho. Para hospedar reuniões de até 1000 usuários, você precisará configurar um pool separado do Skype for Business Server dedicado à Hospedagem de reuniões grandes.
  
Um pool do servidor do Skype for Business dedicado à Hospedagem de reuniões grandes deve hospedar uma e apenas uma reunião de até 1000 usuários ao mesmo tempo, para que os tempos da reunião precisem ser reservados antecipadamente por meio de um processo de agendamento fora da banda para garantir o suporte dedicado da Servidores de front-end. Para dar suporte a mais de uma grande reunião ao mesmo tempo, recomendamos a configuração de vários pools dedicados a grandes reuniões.
  
Para obter mais informações sobre os requisitos de hardware e software e sobre como planejar uma topologia que ofereça suporte a reuniões grandes, consulte [requisitos de hardware e software para conferências no Skype for Business Server](hardware-and-software-requirements.md) e [planeje sua topologia de conferência para Skype for Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implante práticas recomendadas para grandes reuniões

Depois de configurar um pool dedicado para conferências maiores, você pode tomar ações para ajudar a garantir que reuniões maiores no pool forneçam a melhor experiência do usuário. As seções a seguir trazem detalhes sobre como gerenciar reuniões grandes:
  
- Crie organizadores da reunião dedicados
    
- Crie moderadores dedicados
    
- Mantenha um calendário separado para grandes reuniões
    
- Implante um processo de programação de grandes reuniões
    
- Especifique os detalhes de agendamento adequados
    
- Crie uma política de conferência para grandes reuniões
    
### <a name="create-dedicated-meeting-organizers"></a>Crie organizadores da reunião dedicados

Para minimizar o tráfego de comunicação em tempo real no pool de reunião grande, a Microsoft não recomenda a hospedagem de usuários que se conectarão regularmente usando clientes Skype for Business e participar de mensagens instantâneas (IM), presença, conferência e sessões de voz. Pelo contrário, faça uma das seguintes opções:
  
- Crie uma ou mais contas exclusivas apenas para agendar grandes reuniões
    
- Hospede as contas do usuário da equipe responsável por programar grandes reuniões em um pool de grande reuniões
    
### <a name="create-dedicated-moderators"></a>Crie moderadores dedicados

Com centenas a milhares de usuários em uma reunião, é recomendado ter um moderador exclusivo na sessão online da reunião. Essa pessoa dedicada pode ser um representante do organizador da reunião ou membro da equipe de suporte de grande reunião da organização. É importante adicionar o moderador de reunião exclusivo como um apresentador no momento que a reunião é programada, embora seja possível promover um participante online para a função de apresentador enquanto a reunião estiver em andamento.
  
O moderador da reunião pode usar todas as funcionalidades do apresentador dos clientes do Skype for Business para gerenciar a reunião grande. Essas funcionalidades incluem:
  
- Monitorar o lobby e aceitar ou rejeitar usuários no lobby
    
- Remover qualquer usuário da reunião que aí não deveria estar
    
- Alterar os tipos de acesso da reunião
    
- Alterar as funções dos participantes
    
- Convidar participantes adicionais durante a reunião usando a funcionalidade arrastar e soltar, discagem telefônica ou email
    
- Retirar a voz e inserir voz do público ou usuários individuais
    
- Gerenciar o conteúdo da reunião, incluindo carregar conteúdo, excluir conteúdo e trocar o conteúdo ativo

    
### <a name="maintain-a-separate-calendar"></a>Mantenha um calendário separado

Para cada pool de reunião grande, você deve manter um calendário de reuniões grandes agendadas separado nesse pool. Por exemplo, você pode usar uma única conta de usuário no pool de reunião grande e usar o Outlook com o Exchange e o suplemento de reunião online para o Skype for Business para manter um calendário separado. Se você utilizar várias contas de usuário para habilitar uma equipe de suporte para criar reuniões grandes, será necessário configurar um calendário separado que agregue todas as reuniões grandes criadas pelos membros da equipe de suporte. 
  
Manter um calendário de reunião grande separado ajuda a prevenir conflitos e garante que somente uma reunião grande esteja ativa por vez.
  
### <a name="implement-a-scheduling-process"></a>Implante um processo de programação

Como só há suporte para uma reunião grande de cada vez no pool de reunião grande dedicado, você deve implementar um processo de agendamento de reunião grande para facilitar a configuração de reuniões grandes e a evitar conflitos. Essa funcionalidade não é fornecida diretamente pelo Skype for Business Server ou clientes do Skype for Business. Uma maneira de implementar tal processo é usar o sistema de tíquete da equipe de suporte da sua organização, se disponível.
  
Programar uma grande reunião envolve concluir as seguintes etapas:
  
- O organizador da reunião ou representante determina a hora, a duração e o tamanho da uma próxima reunião, além da lista de apresentadores. Se o tamanho da reunião antecipado excede 250 usuários ou para garantir a melhor experiência do usuário para uma reunião com menos de 250 usuários, o organizador ou representante envia uma solicitação para uma grande reunião.
    
- A equipe de programação verifica para ver se a data e hora solicitada está disponível. Como suportamos apenas uma única grande reunião em um pool exclusivo por vez, a equipe de programação precisa verificar o calendário de grandes reuniões para determinar se há outra reunião programada para a data e hora solicitada. Se a hora da reunião está disponível, a equipe aprova a solicitação da reunião.
    
- Se a solicitação for aprovada, a equipe de agendamento (usando as credenciais no pool dedicado) usará o suplemento de reunião online para o Skype for Business com o Outlook para configurar uma reunião no pool de reunião grande dedicado. A URL a ser usada para participar da reunião é fornecida ao requisitante como parte do prompt de aprovação.
    
- O organizador ou representante da reunião usa o Outlook para programar a próxima reunião, adicionando ao convite a URL para participar da reunião. O organizador da reunião ou representante especifica os usuários a serem convidados e envia o convite.
    
### <a name="specify-appropriate-scheduling-details"></a>Especifique os detalhes de agendamento adequados

Depois de fazer uma verificação para assegurar que nenhuma outra reunião esteja agendada na hora solicitada, a equipe de suporte a grandes reuniões, que lida com a solicitação, agenda a reunião no pool de grandes reuniões. 
  
Para garantir a melhor experiência do usuário, é importante agendar a reunião grande com os níveis de acesso certos e as configurações de reunião adequadas às necessidades do organizador da reunião. Considere as seguintes configurações de agendamento definidas nas opções de reunião do Skype for Business:
  
- Use um novo espaço de reunião para cada grande reunião em vez de reutilizar o espaço dedicado da reunião. 
    
- Especifique os níveis de acesso à reunião conforme segue:
    
  - Se pelo menos um convidado for de fora da organização, defina o tipo de reunião como **Para qualquer pessoa (sem restrição)**. Isso habilita você a evitar o gerenciamento de um possível grande lobby quando a reunião estiver em andamento.
    
  - Se a reunião for somente interna, defina o tipo de acesso à reunião como **Para qualquer pessoa da minha organização**.
    
    > [!NOTE]
    > Evite definir o tipo de acesso à reunião como **Pessoas que eu convidar da minha empresa**, pois, quando essa configuração é usada, os organizadores devem adicionar todos os endereços de email em uma lista de convidados e você não poderá convidar um grupo de distribuição. Evite definir o tipo de acesso à reunião como **Apenas eu, o organizador da reunião**, pois essa configuração exige que todos os participantes da reunião, inclusive os apresentadores, sejam colocados no lobby durante a reunião. A pessoa responsável pela execução da grande reunião deverá monitorar a escalação do lobby e aceitar os novos usuários que estiverem no lobby.
  
- Permita que usuários que ligam de telefones entrem na reunião automaticamente marcando a configuração **Chamadores entram diretamente**.
    
- Convide explicitamente os seguintes usuários:
    
  - Organizador e representante da reunião (solicitante)
    
  - A lista de apresentadores fornecida pelo solicitante da reunião
    
    > [!NOTE]
    > Se o tipo de acesso à reunião estiver definido como **Pessoas que eu escolher**, será preciso adicionar explicitamente cada participante da grande reunião como convidado da reunião. 
  
- Gerencie explicitamente os apresentadores, em vez de definir a opção de apresentador como um dos valores promovidos automaticamente. Certifique-se de adicionar os seguintes usuários como apresentadores:
    
  - Organizador e representante da reunião (solicitante)
    
  - A lista de apresentadores fornecida pelo solicitantes da grande reunião
    
    Ao gerenciar explicitamente os apresentadores, é possível controlar o número de apresentadores para que você possa limitá-los a um número pequeno o suficiente para que seja possível conduzir uma grande reunião eficiente. Se a maioria dos participantes da reunião tiver a função de participante, serão reduzidas as chances de alguém acidentalmente assumir o controle da apresentação, excluir a apresentação do PowerPoint, ativar/desativar o áudio dos apresentadores e outras interrupções na reunião. 
    
- Marque a configuração **Desativar o áudio de todos os participantes** para assegurar que apenas os apresentadores possam transmitir áudio para a reunião.
    
- Marque a configuração de **vídeo dos participantes do bloco** para garantir que somente os apresentadores possam transmitir vídeo para a reunião.
    
### <a name="create-a-conferencing-policy"></a>Crie uma política de conferência

Crie uma nova política de conferência específica para grandes reuniões e, depois, atribua a política de conferência aos usuários que estão hospedados no pool dedicado a grandes reuniões. Configure a política de conferência usando os seguintes ajustes:
  
- Defina a opção **MaxMeetingSize** para 1000. (O padrão é 250.)
    
- Defina a opção **AllowLargeMeetings** para **Verdadeiro**. 
    
- Defina a opção **EnableAppDesktopSharing** para **Nenhum**.
    
- Defina a opção **AllowUserToScheduleMeetingsWithAppSharing** para **Falso**.
    
- Defina a opção **AllowSharedNotes** para **Falso**.
    
- Defina a opção **AllowAnnotations** para **Falso**.
    
- Defina a opção **DisablePowerPointAnnotations** para **Verdadeiro**.
    
- Defina a opção **AllowMultiview** para **Falso**.
    
- Defina a opção **EnableMultiviewJoin** para **Falso**.
    
> [!NOTE]
> O suporte para reuniões grandes no Skype for Business Server exige que a configuração **AllowLargeMeetings** seja definida como true. Quando essa configuração é definida como true, a experiência do Skype for Business será otimizada para reuniões muito grandes quando os usuários ingressarem na reunião. Especificamente, em uma reunião grande, o Skype for Business não mostrará a inicial ou a atualização da lista completa de participantes da reunião, o que é um afunilamento de desempenho tanto para o cliente quanto para o Skype for Business Server. Em vez disso, o Skype for Business mostrará apenas informações sobre o usuário e a lista de apresentadores da reunião. O Skype for Business ainda mostrará o número total de participantes disponíveis nas reuniões grandes.

A configuração **$true de AllowLargeMeetings** causa o seguinte:

- Oculta a lista de participantes. 

- Desabilita erros na janela de mensagem instantânea.

- Desabilita o vídeo de vários participantes.

- Desabilita a capacidade de promover um participante ao apresentador. Você deve planejar antecipadamente e declarar todos os apresentadores antes da reunião.

- Desabilita a capacidade de desativar o mudo dos participantes individuais.

- Desabilita a capacidade de aplicar o recurso fixar vídeo em destaque aos participantes.

- Os usuários de discagem PSTN não poderão desativar o mudo usando 6 porque a assistência virtual pessoal que é responsável por comandos DTMF em reuniões grandes grandes está ausente.

- Se o apresentador/organizador agendar uma reunião em que todos devem estar em mudo, primeiro ("ativar mudo"), os usuários PSTN serão ativados durante toda a chamada e não poderão desativar o mudo.

Exceto pela configuração **Tamanho máximo das reuniões**, todas as outras configurações de política de conferência especificadas aqui são obrigatórias para desativar as funcionalidades de conferência que não são necessárias em grandes reuniões.
  
Além disso, você precisa configurar o pool de reunião longa dedicada para que cada usuário do Skype for Business Server que está hospedado no pool e responsável por gerenciar o cronograma da reunião tenha as permissões apropriadas. Para tanto, siga estes passos:
  
- Defina a opção **Designar como apresentador** para **Nenhum**. Normalmente, um ou apenas alguns usuários de todos os participantes em uma grande reunião são apresentadores, então os participantes não devem ser admitidos automaticamente em grandes reuniões como apresentadores. Em vez disso, os apresentadores devem ser designados explicitamente na hora da programação da reunião, ou serem promovidos explicitamente durante uma grande reunião.
    
- Certifique-se de que a caixa de seleção **Tipo de conferência atribuído por padrão** não está selecionada. Esta configuração controla se o suplemento de reunião online do Skype for Business sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as reuniões agendadas têm a mesma URL de junção e informações de áudio. Em cenários de colaboração de pequenos grupos, ter tal tipo de conferência atribuído funciona bem, pois todos têm sua própria conferência atribuída individualmente e a URL de ingresso e informações de áudio constantes ajudam a facilitar um ingresso mais rápido à reunião. No entanto, no caso de grandes reuniões, a equipe as agenda usando um conjunto simples de credenciais de usuário e, depois, fornece URLs de ingresso de informações de áudio para os solicitantes. Neste caso, usar uma URL diferente para ingressar em cada reunião funciona melhor.
    
- Certifique-se de que a caixa de seleção **Admitir usuários anônimos por padrão** não esteja selecionada, a menos que seja obrigatória. Essa configuração afeta o tipo padrão de acesso à reunião agendado pelo suplemento de reunião online para o Skype for Business quando não estiver usando uma conferência atribuída. A opção apropriada para essa configuração depende das necessidades da sua organização. Se a maioria das grandes reuniões da sua organização for interna, não selecione essa opção. Se a maioria das grandes reuniões exigir que usuários externos possam participar, selecione essa opção.
    
Para obter mais informações sobre como criar uma política de conferência, consulte [gerenciar políticas de conferência no Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

