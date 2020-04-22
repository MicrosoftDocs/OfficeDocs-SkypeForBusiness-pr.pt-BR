---
title: Planejar grandes reuniões no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumo: Leia este tópico para saber mais sobre as práticas recomendadas para implementar e gerenciar grandes reuniões no Skype for Business Server.'
ms.openlocfilehash: 18b0f036e49996564aa68735300f4e677ce5b1cb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780230"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planejar grandes reuniões no Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre as práticas recomendadas para implementar e gerenciar grandes reuniões no Skype for Business Server.
  
O tamanho das reuniões que o Skype for Business Server pode dar suporte depende se a conferência está hospedada em um pool compartilhado ou dedicado: em qualquer lugar de 250 participantes de um pool compartilhado para 1000 participantes em um pool dedicado. 
  
> [!NOTE]
> Este tópico se concentra nas práticas recomendadas para grandes reuniões compatíveis com o Skype for Business Server. Se sua organização requer recursos maiores de reunião, você deve considerar a implementação de um ambiente híbrido que aproveita a transmissão de reunião do Skype, um novo serviço online que faz parte do Office 365. 

> [!NOTE]
> A transmissão de reunião do Skype permite que os usuários hospedem e transmitam reuniões para grandes audiências online de até 10.000 participantes. O uso da transmissão de reunião do Skype exige que o Skype for Business Server já esteja configurado em uma configuração híbrida com uma organização de produção 365 do Office. Todos os usuários devem ter um locatário online estabelecido como um pré-requisito. Se você estiver interessado em implantar uma solução híbrida que possa aproveitar a transmissão de reunião do Skype, confira [o que é uma transmissão de reunião do Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) e [configure sua implantação local para transmissão de reunião do Skype](../../deploy/configure-skype-meeting-broadcast.md). 
  
As grandes reuniões geralmente têm as seguintes características:
  
- O formato da reunião é uma apresentação de um-para-muitos.
    
- Um ou alguns usuários são representados e todos eles participam somente como participantes.
    
- O compartilhamento de apresentação do PowerPoint é a principal atividade de colaboração de dados.
    
- O áudio é exigido e o vídeo também pode ser utilizado.
    
- Uma pessoa dedicada, geralmente o organizador da reunião ou um assistente do organizador, configura a reunião com antecedência.
    
- Uma equipe dedicada (não os apresentadores) conduz a reunião, incluindo estabelecer uma conexão para uma reunião online, verificar se o áudio, vídeo e compartilhamento de slides estão funcionando, gerenciar lobby e funções dos usuários, ligar e desligar o microfone dos participantes, responder perguntas e gerenciar gravações, conforme apropriado.
    
Quando um usuário agenda uma reunião, o Skype for Business Server cria um registro no banco de dados de conferência, que armazena dados de conferência, mas não reserva nenhum recurso de hardware para a reunião agendada antes do tempo. Em vez disso, o Skype for Business Server tem lógica de balanceamento de carga interna para alocar dinamicamente recursos de conferência em servidores front-end, de forma que distribua cargas igualmente entre todos os servidores front-end do pool. Isso efetivamente provisiona e usa recursos de hardware, mas é importante que você planeje adequadamente o suporte a reuniões muito grandes. 
  
Por exemplo, quando um pool do Skype for Business Server está sendo executado perto de sua capacidade máxima, cada servidor de front-end pode hospedar aproximadamente 125 reuniões de tamanho médio. Adicionar outra pequena reunião não seria um problema, mas adicionar uma reunião para 1000 os usuários seria um problema, pois os servidores de front-end provavelmente não seriam capazes de oferecer suporte a uma reunião grande, ao mesmo tempo que as outras reuniões de 125.
  
O suporte a grandes reuniões de até 1000 participantes requer a solução de problemas relacionados ao modelo de hardware compartilhado e ao modelo sem reserva. Em geral, você precisa planejar um pool dedicado e seguir as práticas recomendadas, conforme descrito nas seções a seguir. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planejar um pool dedicado

Se sua organização exigir reuniões com mais de 250 participantes, você precisará planejar um pool dedicado para dar suporte à carga. 
  
Para ter recursos suficientes de CPU e memória para reuniões de até 1000 usuários, os servidores front-end de hospedagem não devem hospedar nenhuma outra carga de mensagens instantâneas (IM) e presença ou cargas de trabalho do Enterprise Voice. Os servidores também não devem hospedar nenhuma outra reunião, independentemente do tamanho das outras reuniões. Para hospedar reuniões de até 1000 usuários, você precisa configurar um pool separado do Skype for Business Server dedicado à Hospedagem de grandes reuniões.
  
Um pool do Skype for Business Server dedicado à Hospedagem de grandes reuniões deve hospedar apenas uma reunião de até 1000 usuários ao mesmo tempo, de forma que os tempos de reunião precisam ser reservados antecipadamente por meio de um processo de agendamento fora da banda para garantir o suporte dedicado dos servidores front-end. Para dar suporte a mais de uma grande reunião ao mesmo tempo, você deve configurar vários pools de reunião grandes dedicados.
  
Para obter mais informações sobre os requisitos de hardware e software e sobre o planejamento de uma topologia que ofereça suporte a reuniões grandes, consulte [Hardware and Software Requirements for Conferencing in Skype for Business Server](hardware-and-software-requirements.md) e [planeje sua topologia de conferência para o Skype for Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementar as práticas recomendadas para grandes reuniões

Após configurar um pool dedicado para grandes reuniões, você pode executar etapas para ajudar a garantir que grandes reuniões hospedadas no pool forneçam a melhor experiência do usuário. As seções a seguir fornecem diretrizes para gerenciar grandes reuniões:
  
- Criar organizadores de reunião dedicados
    
- Criar moderadores dedicados
    
- Manter um calendário separado de grandes reuniões
    
- Implementar um processo de agendamento de grandes reuniões
    
- Especificar detalhes de agendamento apropriados
    
- Criar uma política de conferência para grandes reuniões
    
### <a name="create-dedicated-meeting-organizers"></a>Criar organizadores de reunião dedicados

Para minimizar o tráfego de comunicação em tempo real no pool de grandes reuniões, a Microsoft não recomenda a hospedagem de usuários que entram regularmente usando clientes do Skype for Business e participam de mensagens instantâneas (IM), presença, conferência e sessões de voz. Em vez disso, siga um destes procedimentos:
  
- Criar uma ou mais contas de usuário dedicadas apenas para agendar grandes reuniões
    
- Casa as contas de usuário da equipe responsável por agendar grandes reuniões em um pool de grandes reuniões
    
### <a name="create-dedicated-moderators"></a>Criar moderadores dedicados

Com centenas de milhares de usuários em uma reunião, é uma boa prática ter uma pessoa dedicada moderado a sessão online de uma grande reunião. Essa pessoa dedicada pode ser um representante do organizador da reunião ou um membro da equipe de suporte de grande porte da organização. É importante adicionar o moderador de reunião dedicada como apresentador no momento em que a reunião é agendada, embora seja possível promover um participante da reunião online para a função do apresentador enquanto a reunião está em andamento.
  
O moderador da reunião pode usar todas as funcionalidades do apresentador dos clientes do Skype for Business para gerenciar a reunião grande. Essas funcionalidades incluem:
  
- Monitorar o lobby e o admissão ou rejeitar usuários no lobby
    
- Remover qualquer usuário da reunião que não deve estar na reunião
    
- Alterar os tipos de acesso à reunião
    
- Alterar funções de participante
    
- Convidar participantes adicionais durante a reunião usando a funcionalidade de arrastar e soltar, discagem de telefone ou email
    
- Desativando e desativando a audiência ou usuários individuais
    
- Gerenciar o conteúdo da reunião, incluindo carregar conteúdo, excluir conteúdo e trocar conteúdo ativo

    
### <a name="maintain-a-separate-calendar"></a>Manter um calendário separado

Para cada pool de reunião grande, você deve manter um calendário separado de grandes reuniões agendadas nesse pool. Por exemplo, você pode hospedar uma única conta de usuário no pool de grandes reuniões e usar o Outlook com o Exchange e o suplemento de reunião online para o Skype for Business para manter um calendário separado. Se você utilizar várias contas de usuário para habilitar uma equipe de suporte para criar reuniões grandes, será necessário configurar um calendário separado que agregue todas as reuniões grandes criadas pelos membros da equipe de suporte. 
  
Manter um calendário de reunião grande separado ajuda a prevenir conflitos e garante que somente uma reunião grande esteja ativa por vez.
  
### <a name="implement-a-scheduling-process"></a>Implementar um processo de agendamento

Como só há suporte para uma grande reunião por vez no pool dedicado de reunião grande, você deve implementar um grande processo de agendamento de reunião para facilitar a configuração de grandes reuniões e ajudar a evitar conflitos. Esse recurso não é fornecido diretamente pelo Skype for Business Server ou clientes do Skype for Business. Uma maneira de implementar tal processo é usar o sistema de tíquete da equipe de suporte da sua organização, se disponível.
  
Agendar uma grande reunião envolve concluir as seguintes etapas:
  
- O organizador ou representante da reunião determina o tempo, a duração e o tamanho de uma reunião futura, além da lista de apresentadores. Se o tamanho previsto da reunião exceder 250 usuários ou para garantir a melhor experiência do usuário para uma reunião de menos de 250 usuários, o organizador ou o representante enviará uma solicitação para uma reunião grande.
    
- A equipe de agendamento verifica se a data e hora solicitada estão disponíveis. Como damos suporte apenas a uma única reunião grande no pool dedicado por vez, a equipe de agendamento precisa verificar o calendário de reunião grande para determinar se há outra reunião agendada para a data e hora solicitadas. Se a hora solicitada estiver disponível, a equipe aprovará a solicitação de reunião.
    
- Se a solicitação for aprovada, a equipe de agendamento (usando credenciais no pool dedicado) usará o suplemento reunião online para o Skype for Business com o Outlook para configurar uma reunião no pool dedicado de grandes reuniões. A URL a ser usada para ingressar na reunião é fornecida ao solicitante como parte do aviso de aprovação.
    
- O organizador ou representante da reunião usa o Outlook para agendar a próxima reunião, adicionando a URL para participar da reunião ao convite da reunião. O organizador ou o representante da reunião especificará os usuários a serem convidados e enviarão o convite da reunião.
    
### <a name="specify-appropriate-scheduling-details"></a>Especificar detalhes de agendamento apropriados

Depois de fazer uma verificação para assegurar que nenhuma outra reunião esteja agendada na hora solicitada, a equipe de suporte a grandes reuniões, que lida com a solicitação, agenda a reunião no pool de grandes reuniões. 
  
Para garantir a melhor experiência do usuário, é importante agendar a grande reunião com os níveis de acesso corretos e as configurações de reunião adequadas às necessidades do organizador da reunião. Considere as seguintes configurações de agendamento definidas nas opções de reunião do Skype for Business:
  
- Use um novo espaço de reunião para cada grande reunião em vez de reutilizar o espaço dedicado da reunião. 
    
- Especifique os níveis de acesso à reunião conforme segue:
    
  - Se pelo menos um convidado for externo à organização, defina o tipo de acesso à reunião como **qualquer pessoa (sem restrições)**. Isso permite que você evite ter que gerenciar um possível grande saguão quando a reunião estiver em andamento.
    
  - Se a reunião for somente interna, defina o tipo de acesso à reunião como **Para qualquer pessoa de minha organização**.
    
    > [!NOTE]
    > Evite definir o tipo de acesso à reunião como **Pessoas que eu convidar da minha empresa**, pois quando essa configuração é usada, os organizadores devem adicionar os endereços de email de todos os usuários à lista de convidados e você não pode convidar um grupo de distribuição. Evite definir o tipo de acesso à reunião como **Apenas eu, o organizador da reunião**, pois esta configuração exige que todos os participantes da reunião, inclusive apresentadores, sejam colocados no saguão no tempo de execução da reunião. A pessoa responsável pela execução da grande reunião deverá monitorar a escalação do saguão e aceitar os novos usuários que estão no saguão.
  
- Permita que usuários ligando de telefones entrem na reunião automaticamente marcando a configuração **Chamadores entram diretamente**.
    
- Convide explicitamente os seguintes usuários:
    
  - Organizador e representante da reunião (solicitante)
    
  - A lista de apresentadores fornecida pelo solicitante da reunião
    
    > [!NOTE]
    > Se o tipo de acesso à reunião estiver definido como **Pessoas que eu escolher**, será preciso adicionar explicitamente cada participante da grande reunião como convidado da reunião. 
  
- Gerencie explicitamente os apresentadores, em vez de definir a opção de apresentador como um dos valores promovidos automaticamente. Certifique-se de adicionar os seguintes usuários como apresentadores:
    
  - Organizador e representante da reunião (solicitante)
    
  - A lista de apresentadores fornecida pelo solicitantes da grande reunião
    
    Ao gerenciar explicitamente os apresentadores, você pode limitar os apresentadores a um número pequeno o suficiente para possibilitar uma reunião grande eficaz. Se a maioria dos participantes da reunião tiverem a função de participante, isso ajudará a reduzir as chances de alguém acidentalmente assumir o controle da apresentação, excluindo a apresentação do PowerPoint, ativando/desativando o áudio dos apresentadores e outras interrupções na reunião. 
    
- Marque a configuração **Desativar o áudio de todos os participantes** para assegurar que apenas os apresentadores possam transmitir áudio para a reunião.
    
- Marque a configuração **Bloquear vídeo dos participantes** para garantir que apenas os apresentadores possam transmitir vídeo para a reunião.
    
### <a name="create-a-conferencing-policy"></a>Criar uma política de conferência

Crie uma nova política de conferência especificamente para grandes reuniões e, em seguida, atribua a política de conferência aos usuários hospedados no pool dedicado de grandes reuniões. Configure a política de conferência usando as seguintes configurações:
  
- Defina a opção **MaxMeetingSize** para 1000. (O padrão é 250).
    
- Defina a opção **AllowLargeMeetings** como **true**. 
    
- Defina a opção **EnableAppDesktopSharing** para **nenhum**.
    
- Defina a opção **AllowUserToScheduleMeetingsWithAppSharing** para **falso**.
    
- Defina a opção **AllowSharedNotes** para **falso**.
    
- Defina a opção **AllowAnnotations** para **falso**.
    
- Defina a opção **DisablePowerPointAnnotations** como **true**.
    
- Defina a opção **AllowMultiview** para **falso**.
    
- Defina a opção **EnableMultiviewJoin** para **falso**.
    
> [!NOTE]
> O suporte para grandes reuniões no Skype for Business Server exige que a configuração **AllowLargeMeetings** seja definida como true. Quando essa configuração é definida como true, a experiência do Skype for Business será otimizada para reuniões de grande porte, quando os usuários ingressarem na reunião. Especificamente, em uma grande reunião, o Skype for Business não mostrará a inicial ou a atualização da lista de participantes da reunião completa, que é um afunilamento de desempenho para o cliente e o Skype for Business Server. Em vez disso, o Skype for Business mostrará apenas informações sobre o usuário e a lista de apresentadores da reunião. O Skype for Business ainda mostrará o número total de participantes disponíveis nas grandes reuniões.

A configuração de **$true AllowLargeMeetings** causa o seguinte:

- Oculta a lista de participantes. 

- Desabilita erros na janela de mensagens instantâneas.

- Desabilita o vídeo de vários participantes.

- Desabilita a capacidade de promover um participante para o apresentador. Você deve planejar antecipadamente e declarar todos os apresentadores antes da reunião.

- Desabilita a capacidade de desativar o mudo de participantes individuais.

- Desabilita a capacidade de aplicar o recurso de bloqueio de destaque de vídeo aos participantes.

- Discagem PSTN os usuários não poderão desativar o áudio usando 6 porque a assistência virtual pessoal que é responsável por comandos DTMF em grandes reuniões ativas está ausente.

- Se o apresentador/organizador agendar uma reunião em que todos devem ser ativados por telefone ("sem áudio"), os usuários PSTN serão ativados por toda a chamada e não poderão desativar o áudio.

Com exceção da configuração do **tamanho máximo da reunião** , todas as outras configurações de política de conferência especificadas aqui são necessárias para desabilitar os recursos de conferência que não são necessários em grandes reuniões.
  
Além disso, você precisa configurar o pool de reunião grande dedicado para que cada usuário do Skype for Business Server hospedado no pool e responsável pelo gerenciamento da agenda da reunião tenha as permissões apropriadas. Para tanto, siga estes passos:
  
- Defina a opção **designar como apresentador** como **nenhum**. Normalmente, um ou apenas alguns usuários de todos os participantes de uma grande reunião são os apresentadores, portanto, os participantes não devem ser admitidos automaticamente em grandes reuniões como apresentadores. Em vez disso, os apresentadores devem ser explicitamente designados no horário do plano de reunião ou ser promovidos explicitamente durante a grande reunião.
    
- Certifique-se de que a caixa de seleção **tipo de conferência atribuído por padrão** não esteja selecionada. Esta configuração controla se o suplemento de reunião online para o Skype for Business sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as reuniões agendadas têm a mesma URL de ingresso e informações de áudio. Em pequenos cenários de colaboração de grupo, ter esse tipo de conferência atribuído funciona bem porque todos têm sua própria conferência atribuída individualmente e a URL de ingresso e as informações de áudio constantes ajudam a facilitar a reunião mais rápida. No entanto, no cenário de reunião grande, a equipe de suporte de grande reunião agenda as grandes reuniões usando um único conjunto de credenciais de usuário e, em seguida, fornece URLs de ingresso e informações de áudio aos solicitantes da reunião. Nesse caso, o uso de uma URL diferente para ingressar em cada reunião funciona melhor.
    
- Certifique-se de que a caixa de seleção **admitir usuários anônimos por padrão** não esteja selecionada, a menos que seja necessária. Essa configuração afeta o tipo de acesso de reunião padrão agendado pelo suplemento reunião online para o Skype for Business quando não estiver usando uma conferência atribuída. A opção apropriada para essa configuração depende das necessidades da sua organização. Se a maioria das grandes reuniões da sua organização forem reuniões internas, não selecione essa opção. Se a maioria das reuniões grandes exigir que usuários externos possam participar, selecione essa opção.
    
Para obter mais informações sobre como criar uma política de conferência, consulte [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

