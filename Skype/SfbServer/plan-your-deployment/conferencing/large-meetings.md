---
title: Planejar para grandes reuniões em Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumo: Leia este tópico para saber mais sobre práticas recomendadas para implementar e gerenciar grandes reuniões em Skype para Business Server.'
ms.openlocfilehash: 32faf7627ddcc691f95bab616a59cf008393b360
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920465"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planejar para grandes reuniões em Skype para Business Server
 
**Resumo:** Leia este tópico para saber mais sobre práticas recomendadas para implementar e gerenciar grandes reuniões em Skype para Business Server.
  
O tamanho de reuniões que suporta o Skype para Business Server depende se a conferência está hospedada em um pool compartilhado ou dedicado: em qualquer lugar de 250 participantes em um pool compartilhado aos participantes de 1000 em um pool dedicado. 
  
> [!NOTE]
> Este tópico se concentra em práticas recomendadas para grandes reuniões suportados pelo Skype para Business Server. Se sua organização requer maiores capacidades de reunião, você deve considerar a implementação de um ambiente híbrido que tiram vantagens do Skype transmitir reunião, um novo serviço online que faz parte do Office 365. 

> [!NOTE]
> A Transmissão de Reunião do Skype habilita os usuários a hospedarem e divulgarem a grandes públicos online reuniões com até 10.000 participantes. O uso de Transmissão de Reunião do Skype exige que o Skype for Business Server esteja configurado como híbrido em um locatário do Office 365 de produção. Todos os usuários devem estabelecer um locatário online, isso é um pré-requisito. Se você está interessado Implantando uma solução híbrida que podem tirar proveito da transmissão do Skype reunião, consulte [o que é uma transmissão do Skype reunião?](https://go.microsoft.com/fwlink/?LinkId=617071) e [configurar sua implantação no local para transmissão do Skype reunião](../../deploy/configure-skype-meeting-broadcast.md). 
  
Grandes reuniões costumam ter as seguintes características:
  
- O formato da reunião é uma apresentação de um-para-muitos.
    
- Um ou alguns usuários são representados e todos eles participam somente como participantes.
    
- O compartilhamento de apresentação do PowerPoint é a principal atividade de colaboração de dados.
    
- O áudio é exigido e o vídeo também pode ser utilizado.
    
- Uma pessoa dedicada, geralmente o organizador da reunião ou um assistente do organizador, configura a reunião com antecedência.
    
- Uma equipe dedicada (não os apresentadores) conduz a reunião, incluindo estabelecer uma conexão para uma reunião online, verificar se o áudio, vídeo e compartilhamento de slides estão funcionando, gerenciar lobby e funções dos usuários, ligar e desligar o microfone dos participantes, responder perguntas e gerenciar gravações, conforme apropriado.
    
Quando um usuário agenda uma reunião, Skype para Business Server cria um registro no banco de dados de conferência, que armazena dados de conferência, mas não reserva quaisquer recursos de hardware para a reunião agendada antecipadamente. Em vez disso, Skype para Business Server tem lógica para alocar dinamicamente os recursos de conferência nos servidores Front-End, de forma que distribui cargas igualmente entre todos os servidores Front-End do pool de balanceamento de carga interna. Isso provisiona e usa com eficiência os recursos de hardware, mas é importante que você planeje adequadamente o suporte para reuniões muito grandes. 
  
Por exemplo, quando um Skype para pool de servidores de negócios está sendo executado e está perto sua capacidade superior, cada servidor Front-End pode hospedar aproximadamente 125 reuniões de médio porte. Adicionar outra reunião pequena não seria problema, mas adicionar uma reunião para 1.000 usuários, sim, pois os Servidores Front-End provavelmente não seriam compatíveis com tal reunião grande ao mesmo tempo que as outras 125 reuniões.
  
O suporte a grandes reuniões de até 1.000 participantes exige lidar com os problemas relacionados tanto ao modelo de hardware compartilhado quanto ao modelo sem reserva. Em geral, você precisará planejar um pool dedicado e siga as práticas recomendadas, conforme descrito nas seções a seguir. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planeje um pool dedicado

Se a sua organização requer reuniões com mais de 250 participantes, será necessário planejar um pool dedicado para suportar a carga. 
  
Para ter recursos de CPU e memória suficientes para as reuniões com até 1.000 usuários, os Servidores Front-End de hospedagem não devem hospedar nenhuma outra carga de trabalho de mensagens instantâneas (IM) e presença nem do Enterprise Voice. Os servidores também não devem hospedar nenhuma outra reunião, independente do tamanho. Para hospedar reuniões de até 1.000 usuários, você precisará configurar um Skype separado para pool de servidores de negócios dedicado à hospedagem de grandes reuniões.
  
Um Skype para pool de servidores de negócios dedicado à hospedagem de grandes reuniões deve hospedar um e apenas uma reunião de até 1.000 usuários ao mesmo tempo, então os horários de reuniões precisar ser reservado antecipadamente por meio de um limite da faixa de agendamento de processo para garantir o suporte dedicado do Servidores de Front-End. Para dar suporte a mais de uma grande reunião ao mesmo tempo, recomendamos a configuração de vários pools dedicados a grandes reuniões.
  
Para obter mais informações sobre planejamento e requisitos de software e hardware uma topologia que suporta a grandes reuniões, consulte [requisitos de Hardware e software para conferências no Skype para Business Server](hardware-and-software-requirements.md) e [planejar sua topologia de conferência para Skype para Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implante práticas recomendadas para grandes reuniões

Depois de configurar um pool dedicado para conferências maiores, você pode tomar ações para ajudar a garantir que reuniões maiores no pool forneçam a melhor experiência do usuário. As seções a seguir trazem detalhes sobre como gerenciar reuniões grandes:
  
- Crie organizadores da reunião dedicados
    
- Crie moderadores dedicados
    
- Mantenha um calendário separado para grandes reuniões
    
- Implante um processo de programação de grandes reuniões
    
- Especifique os detalhes de agendamento adequados
    
- Crie uma política de conferência para grandes reuniões
    
### <a name="create-dedicated-meeting-organizers"></a>Crie organizadores da reunião dedicados

Para minimizar o tráfego de comunicação em tempo real do pool de reunião grande, a Microsoft não recomenda hospedando os usuários que regularmente entrar usando o Skype para clientes corporativos e participarem de mensagens instantâneas (IM), presença, conferência e sessões de voz. Pelo contrário, faça uma das seguintes opções:
  
- Crie uma ou mais contas exclusivas apenas para agendar grandes reuniões
    
- Hospede as contas do usuário da equipe responsável por programar grandes reuniões em um pool de grande reuniões
    
### <a name="create-dedicated-moderators"></a>Crie moderadores dedicados

Com centenas a milhares de usuários em uma reunião, é recomendado ter um moderador exclusivo na sessão online da reunião. Essa pessoa dedicada pode ser um representante do organizador da reunião ou um membro da equipe de suporte de reunião grande da organização. É importante adicionar o moderador de reunião exclusivo como um apresentador no momento que a reunião é programada, embora seja possível promover um participante online para a função de apresentador enquanto a reunião estiver em andamento.
  
Moderador reunião pode usar todas as funcionalidades do apresentador do Skype para clientes de negócios para gerenciar grandes reuniões. Essas funcionalidades incluem:
  
- Monitorar o lobby e aceitar ou rejeitar usuários no lobby
    
- Remover qualquer usuário da reunião que aí não deveria estar
    
- Alterar os tipos de acesso da reunião
    
- Alterar as funções dos participantes
    
- Convidar mais participantes durante a reunião usando arrastar e soltar funcionalidade, discagem de telefone ou email
    
- Retirar a voz e inserir voz do público ou usuários individuais
    
- Gerenciar o conteúdo da reunião, incluindo carregar conteúdo, excluir conteúdo e trocar o conteúdo ativo

    
### <a name="maintain-a-separate-calendar"></a>Mantenha um calendário separado

Para cada pool de reunião grande, você deve manter um calendário de reuniões grandes agendadas separado nesse pool. Por exemplo, você pode hospedar uma única conta de usuário no pool de reunião grande e usar o Outlook com o Exchange e o suplemento de Reunião Online para Skype for Business para manter um calendário separado. Se você utilizar várias contas de usuário para habilitar uma equipe de suporte para criar reuniões grandes, será necessário configurar um calendário separado que agregue todas as reuniões grandes criadas pelos membros da equipe de suporte. 
  
Manter um calendário de reunião grande separado ajuda a prevenir conflitos e garante que somente uma reunião grande esteja ativa por vez.
  
### <a name="implement-a-scheduling-process"></a>Implante um processo de programação

Como apenas uma grande reunião por vez é suportada no pool dedicado grande reunião, você deve implementar uma grande reunião processo para facilitar a configuração de grandes reuniões e ajudar a evitar conflitos de agendamento. Esse recurso não for fornecido diretamente pelo Skype para Business Server ou Skype para clientes corporativos. Uma maneira de implementar um processo é usar o sistema de registro da equipe de suporte da sua organização, se disponível.
  
Programar uma grande reunião envolve concluir as seguintes etapas:
  
- O organizador da reunião ou representante determina a hora, a duração e o tamanho da uma próxima reunião, além da lista de apresentadores. Se o tamanho da reunião antecipado excede 250 usuários ou para garantir a melhor experiência do usuário para uma reunião com menos de 250 usuários, o organizador ou representante envia uma solicitação para uma grande reunião.
    
- A equipe de programação verifica para ver se a data e hora solicitada está disponível. Como suportamos apenas uma única grande reunião em um pool exclusivo por vez, a equipe de programação precisa verificar o calendário de grandes reuniões para determinar se há outra reunião programada para a data e hora solicitada. Se a hora da reunião está disponível, a equipe aprova a solicitação da reunião.
    
- Se a solicitação for aprovada, a equipe de agendamento (usando credenciais no pool dedicado) usa o suplemento de Reunião Online para Skype for Business com o Outlook para agendar uma reunião no pool dedicado reunião grande. A URL a ser usada para participar da reunião é fornecida ao requisitante como parte do prompt de aprovação.
    
- O organizador ou representante da reunião usa o Outlook para programar a próxima reunião, adicionando ao convite a URL para participar da reunião. O organizador da reunião ou representante especifica os usuários a serem convidados e envia o convite.
    
### <a name="specify-appropriate-scheduling-details"></a>Especifique os detalhes de agendamento adequados

Depois de fazer uma verificação para assegurar que nenhuma outra reunião esteja agendada na hora solicitada, a equipe de suporte a grandes reuniões, que lida com a solicitação, agenda a reunião no pool de grandes reuniões. 
  
Para garantir a melhor experiência de usuário, é importante agendar a reunião grande com os níveis de acesso à direita e configurações de reunião adequadas às necessidades do organizador da reunião. Considere as seguintes configurações de agendamento configuradas no Skype para opções de reunião de negócios:
  
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
    
- Verifique o **Bloquear vídeo dos participantes** a definição para certificar-se de que apenas os apresentadores possam transmitir vídeo para a reunião.
    
### <a name="create-a-conferencing-policy"></a>Crie uma política de conferência

Crie uma nova política de conferência específica para grandes reuniões e, depois, atribua a política de conferência aos usuários que estão hospedados no pool dedicado a grandes reuniões. Configure a política de conferência usando os seguintes ajustes:
  
- Defina a opção de **MaxMeetingSize** a 1000. (O padrão é 250.)
    
- Defina a opção **AllowLargeMeetings** para **Verdadeiro**. 
    
- Defina a opção **EnableAppDesktopSharing** para **Nenhum**.
    
- Defina a opção **AllowUserToScheduleMeetingsWithAppSharing** para **Falso**.
    
- Defina a opção **AllowSharedNotes** para **Falso**.
    
- Defina a opção **AllowAnnotations** para **Falso**.
    
- Defina a opção **DisablePowerPointAnnotations** para **Verdadeiro**.
    
- Defina a opção **AllowMultiview** para **Falso**.
    
- Defina a opção **EnableMultiviewJoin** para **Falso**.
    
> [!NOTE]
> Suporte para grandes reuniões em Skype para Business Server requer que a configuração de **AllowLargeMeetings** seja definido como true. Quando essa configuração estiver definida como true, o Skype para experiência de negócios será otimizada para reuniões extra grandes quando os usuários ingressem na reunião. Especificamente, em uma reunião grande, Skype para negócios não mostrará a atualização da lista de participantes completo de reunião, que é um gargalo de desempenho para o cliente e Skype para Business Server ou inicial. Em vez disso, o Skype para negócios mostrará apenas informações sobre o usuário e a lista de apresentadores da reunião. Skype para negócios ainda mostrará o número total de participantes disponíveis em grandes reuniões.

A configuração - AllowLargeMeetings $true faz com que o seguinte: · Oculta a lista de participação do participante. · Desabilita os erros na janela de mensagens Instantâneas.
· Desabilita o vídeo com vários participante.
· Desabilita a capacidade de promover um participante a apresentador. Você deve planejar com antecedência e declarar todos os apresentadores antes da reunião.
· Desabilita a capacidade de desativar o mudo de participantes individuais.
· Desabilita a capacidade de aplicar o recurso de bloqueio destaque de vídeo aos participantes.
· Discagem PSTN em usuários, será possível desativar o mudo usando * 6 porque pessoais assistência Virtual que é responsável por DTMF comandos no active grandes reuniões está faltando.
· Se o apresentador/organizador agenda uma reunião onde todos devem ser ativado primeiro ("mudo All"), usuários PSTN serão ativados em toda a chamada e não será capazes de desativar o mudo.

Exceto pela configuração **Tamanho máximo das reuniões**, todas as outras configurações de política de conferência especificadas aqui são obrigatórias para desativar as funcionalidades de conferência que não são necessárias em grandes reuniões.
  
Além disso, você precisará configurar o pool de reunião grande dedicado, de modo que cada Skype para usuário Business Server quem é responsável por gerenciar o agendamento de reunião e de hospedados no pool tem as permissões apropriadas. Para tanto, siga estes passos:
  
- Defina a opção **Designar como apresentador** para **Nenhum**. Normalmente, um ou apenas alguns usuários de todos os participantes em uma grande reunião são apresentadores, então os participantes não devem ser admitidos automaticamente em grandes reuniões como apresentadores. Em vez disso, os apresentadores devem ser designados explicitamente na hora da programação da reunião, ou serem promovidos explicitamente durante uma grande reunião.
    
- Certifique-se de que a caixa de seleção **Tipo de conferência atribuído por padrão** não está selecionada. Essa configuração controla se o suplemento de Reunião Online para Skype para negócios sempre agenda conferências com o uso do organizador atribuído a conferência, que significa que as reuniões programadas ter a mesma URL de ingresso e informações de áudio. Em cenários de colaboração de pequenos grupos, ter tal tipo de conferência atribuído funciona bem, pois todos têm sua própria conferência atribuída individualmente e a URL de ingresso e informações de áudio constantes ajudam a facilitar um ingresso mais rápido à reunião. No entanto, no caso de grandes reuniões, a equipe as agenda usando um conjunto simples de credenciais de usuário e, depois, fornece URLs de ingresso de informações de áudio para os solicitantes. Neste caso, usar uma URL diferente para ingressar em cada reunião funciona melhor.
    
- Certifique-se de que a caixa de seleção **Admitir usuários anônimos por padrão** não esteja selecionada, a menos que seja obrigatória. Esta configuração afeta o padrão de reuniões agendado pelo suplemento de Reunião Online para Skype para os negócios, quando não usando uma conferência atribuída do tipo de acesso. A opção adequada para essa configuração depende da necessidades da sua organização. Se a maioria das grandes reuniões da sua organização for interna, não selecione essa opção. Se a maioria das grandes reuniões exigir que usuários externos possam participar, selecione essa opção.
    
Para obter mais informações sobre como criar uma política de conferência, consulte [Gerenciar políticas de conferência no Skype para Business Server](../../manage/conferencing/conferencing-policies.md).
  

