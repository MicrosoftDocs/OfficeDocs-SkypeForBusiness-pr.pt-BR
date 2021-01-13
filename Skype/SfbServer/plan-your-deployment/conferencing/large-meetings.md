---
title: Planejar grandes reuniões no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 'Resumo: Leia este tópico para saber mais sobre as práticas recomendadas para implementar e gerenciar grandes reuniões no Skype for Business Server.'
ms.openlocfilehash: 8e982f08b1ff65ac6a4ea6f47a15e57f1eded163
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813971"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Planejar grandes reuniões no Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre as práticas recomendadas para implementar e gerenciar grandes reuniões no Skype for Business Server.
  
O tamanho das reuniões que o Skype for Business Server pode suportar depende se a conferência está hospedada em um pool compartilhado ou dedicado: em qualquer lugar, de 250 participantes em um pool compartilhado a 1.000 participantes em um pool dedicado. 
  
> [!NOTE]
> Este tópico se concentra nas práticas recomendadas para grandes reuniões com suporte do Skype for Business Server. Se sua organização exigir recursos maiores de reunião, considere a implementação de um ambiente híbrido que aproveite a Transmissão de Reunião do Skype, um novo serviço online que faz parte do Microsoft 365 e do Office 365. 

> [!NOTE]
> A Transmissão de Reunião do Skype permite que os usuários hospedem e transdiem reuniões para grandes audiências online de até 10.000 participantes. O uso da Transmissão de Reunião do Skype exige que o Skype for Business Server já tenha sido configurado em uma configuração híbrida com uma organização de produção do Microsoft 365 ou Office 365. Todos os usuários devem ter um locatário online estabelecido como pré-requisito. Se você estiver interessado em implantar uma solução híbrida que possa aproveitar a Transmissão de Reunião do Skype, consulte O que é uma Transmissão de Reunião do [Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) e Configure sua implantação local para a Transmissão de Reunião do [Skype.](../../deploy/configure-skype-meeting-broadcast.md) 
  
Reuniões grandes geralmente têm as seguintes características:
  
- O formato da reunião é uma apresentação de um-para-muitos.
    
- Um ou alguns usuários são representados e todos eles participam somente como participantes.
    
- O compartilhamento de apresentação do PowerPoint é a principal atividade de colaboração de dados.
    
- O áudio é exigido e o vídeo também pode ser utilizado.
    
- Uma pessoa dedicada, geralmente o organizador da reunião ou um assistente do organizador, configura a reunião com antecedência.
    
- Uma equipe dedicada (não os apresentadores) conduz a reunião, incluindo estabelecer uma conexão para uma reunião online, verificar se o áudio, vídeo e compartilhamento de slides estão funcionando, gerenciar lobby e funções dos usuários, ligar e desligar o microfone dos participantes, responder perguntas e gerenciar gravações, conforme apropriado.
    
Quando um usuário agenda uma reunião, o Skype for Business Server cria um registro no banco de dados de conferência, que armazena dados de conferência, mas não reserva nenhum recurso de hardware para a reunião agendada com antecedência. Em vez disso, o Skype for Business Server tem lógica de balanceamento de carga interna para alocar dinamicamente recursos de conferência nos Servidores Front-End de uma maneira que distribua cargas igualmente entre todos os Servidores Front-End no pool. Isso provisiona e usa efetivamente recursos de hardware, mas é importante que você planeje adequadamente o suporte a reuniões muito grandes. 
  
Por exemplo, quando um pool do Skype for Business Server está sendo executado perto de sua capacidade máxima, cada Servidor Front End pode hospedar aproximadamente 125 reuniões de tamanho médio. Adicionar outra reunião pequena não seria um problema, mas adicionar uma reunião para 1.000 usuários seria um problema porque os Servidores front-end provavelmente não seriam capazes de suportar tal reunião grande ao mesmo tempo que as outras 125 reuniões.
  
O suporte a grandes reuniões de até 1.000 participantes requer a abordagem dos problemas relacionados ao modelo de hardware compartilhado e ao modelo sem reserva. Em geral, você precisa planejar um pool dedicado e seguir as práticas recomendadas conforme descrito nas seções a seguir. 
  
## <a name="plan-for-a-dedicated-pool"></a>Planejar um pool dedicado

Se sua organização exigir reuniões com mais de 250 participantes, será necessário planejar um pool dedicado para suportar a carga. 
  
Para ter recursos suficientes de CPU e memória para reuniões de até 1.000 usuários, os Servidores front-end de hospedagem não devem hospedar qualquer outra mensagem instantânea (IM) e presença ou cargas de trabalho do Enterprise Voice. Os servidores também não devem hospedar outras reuniões, independentemente do tamanho das outras reuniões. Para hospedar reuniões de até 1.000 usuários, você precisa configurar um pool separado do Skype for Business Server dedicado à hospedagem de grandes reuniões.
  
Um pool do Skype for Business Server dedicado a hospedar grandes reuniões deve hospedar uma e apenas uma reunião de até 1.000 usuários ao mesmo tempo, portanto, os horários das reuniões precisam ser reservados com antecedência por meio de um processo de agendamento fora de banda para garantir o suporte dedicado dos Servidores Front-End. Para dar suporte a mais de uma grande reunião ao mesmo tempo, você deve configurar vários pools dedicados a grandes reuniões.
  
Para obter mais informações sobre os requisitos de hardware e software e planejar uma topologia que oferece suporte a grandes reuniões, consulte Requisitos de hardware e software para conferência no [Skype for Business Server](hardware-and-software-requirements.md) e planeje sua topologia de conferência para o Skype for Business [Server.](conferencing-topology.md)
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementar práticas recomendadas para grandes reuniões

Depois de configurar um pool dedicado para grandes reuniões, você pode tomar medidas para ajudar a garantir que reuniões grandes hospedadas no pool forneçam a melhor experiência do usuário. As seções a seguir fornecem diretrizes para gerenciar grandes reuniões:
  
- Criar organizadores de reunião dedicados
    
- Criar moderadores dedicados
    
- Manter um calendário separado de grandes reuniões
    
- Implementar um processo de agendamento de grandes reuniões
    
- Especificar detalhes de agendamento apropriados
    
- Criar uma política de conferência para grandes reuniões
    
### <a name="create-dedicated-meeting-organizers"></a>Criar organizadores de reunião dedicados

Para minimizar o tráfego de comunicações em tempo real no pool de grandes reuniões, a Microsoft não recomenda hospedar usuários que se inscrevam regularmente usando clientes do Skype for Business e participam de mensagens instantâneas (IM), presença, conferência e sessões de voz. Em vez disso, faça um dos seguintes:
  
- Criar uma ou mais contas de usuário dedicadas apenas para agendar grandes reuniões
    
- Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool
    
### <a name="create-dedicated-moderators"></a>Criar moderadores dedicados

Com centenas a milhares de usuários em uma reunião, é uma boa prática ter uma pessoa dedicada para moderar a sessão online de uma grande reunião. Essa pessoa dedicada pode ser um representante do organizador da reunião ou um membro da equipe de suporte a grandes reuniões da organização. É importante adicionar o moderador dedicado da reunião como apresentador no momento em que a reunião está agendada, embora seja possível promover um participante da reunião online para a função de apresentador enquanto a reunião está em andamento.
  
O moderador da reunião pode usar todas as funcionalidades de apresentador dos clientes do Skype for Business para gerenciar a grande reunião. Essas funcionalidades incluem:
  
- Monitorando o lobby e admissão ou rejeição de usuários no lobby
    
- Removendo todos os usuários da reunião que não deveriam estar na reunião
    
- Alterar os tipos de acesso à reunião
    
- Alterando funções de participante
    
- Convidar participantes adicionais durante a reunião usando a funcionalidade arrastar e soltar, discagem por telefone ou email
    
- Muting and unmuting the audience or individual users
    
- Gerenciar o conteúdo da reunião, incluindo carregar conteúdo, excluir conteúdo e alternar conteúdo ativo

    
### <a name="maintain-a-separate-calendar"></a>Manter um calendário separado

Para cada pool de grandes reuniões, você deve manter um calendário separado de grandes reuniões agendadas nesse pool. Por exemplo, você pode ter uma única conta de usuário no pool de grandes reuniões e usar o Outlook com o Exchange e o Online Meeting Add-in para Skype for Business para manter um calendário separado. Se você utilizar várias contas de usuário para habilitar uma equipe de suporte para criar reuniões grandes, será necessário configurar um calendário separado que agregue todas as reuniões grandes criadas pelos membros da equipe de suporte. 
  
Manter um calendário de reunião grande separado ajuda a prevenir conflitos e garante que somente uma reunião grande esteja ativa por vez.
  
### <a name="implement-a-scheduling-process"></a>Implementar um processo de agendamento

Como apenas uma grande reunião por vez é suportada no pool de reunião grande dedicado, você deve implementar um grande processo de agendamento de reunião para facilitar a configuração de grandes reuniões e ajudar a evitar conflitos. Esse recurso não é fornecido diretamente pelo Skype for Business Server ou clientes do Skype for Business. Uma maneira de implementar esse processo é usar o sistema de tíquetes da equipe de suporte da sua organização, se disponível.
  
Agendar uma grande reunião envolve concluir as seguintes etapas:
  
- O organizador ou representante da reunião determina o tempo, a duração e o tamanho de uma próxima reunião, além da lista de apresentadores. Se o tamanho antecipado da reunião exceder 250 usuários ou para garantir a melhor experiência do usuário para uma reunião com menos de 250 usuários, o organizador ou representante enviará uma solicitação para uma grande reunião.
    
- A equipe de agendamento verifica se a data e a hora solicitadas estão disponíveis. Como suportamos apenas uma única grande reunião no pool dedicado por vez, a equipe de agendamento precisa verificar o calendário de grandes reuniões para determinar se há outra reunião agendada para a data e a hora solicitadas. Se o horário solicitado estiver disponível, a equipe aprovará a solicitação de reunião.
    
- Se a solicitação for aprovada, a equipe de agendamento (usando credenciais no pool dedicado) usará o Complemento de Reunião Online do Skype for Business com o Outlook para configurar uma reunião em um pool dedicado a grandes reuniões. A URL a ser usada para ingressar na reunião é fornecida ao solicitante como parte do aviso de aprovação.
    
- O organizador ou representante da reunião usa o Outlook para agendar a próxima reunião, adicionando a URL para ingressar na reunião ao convite da reunião. O organizador ou representante da reunião especifica os usuários a serem convidados e envia o convite da reunião.
    
### <a name="specify-appropriate-scheduling-details"></a>Especificar detalhes de agendamento apropriados

Depois de fazer uma verificação para assegurar que nenhuma outra reunião esteja agendada na hora solicitada, a equipe de suporte a grandes reuniões, que lida com a solicitação, agenda a reunião no pool de grandes reuniões. 
  
Para garantir a melhor experiência do usuário, é importante agendar a grande reunião com os níveis de acesso corretos e as configurações da reunião apropriadas às necessidades do organizador da reunião. Considere as seguintes configurações de agendamento configuradas nas opções de Reunião do Skype for Business:
  
- Use um novo espaço de reunião para cada grande reunião em vez de reutilizar o espaço dedicado da reunião. 
    
- Especifique os níveis de acesso à reunião conforme segue:
    
  - Se pelo menos um convidado for externo à organização, de definir o tipo de acesso à reunião como **Qualquer Pessoa (sem restrições).** Isso permite que você evite ter que gerenciar um possível grande saguão quando a reunião estiver em andamento.
    
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
    
    Ao gerenciar explicitamente os apresentadores, você pode limitar os apresentadores a um número pequeno o suficiente para que seja possível ter uma grande reunião eficaz. Se a maioria dos participantes da reunião tiverem a função de participante, isso ajudará a reduzir as chances de alguém acidentalmente assumir o controle da apresentação, excluindo a apresentação do PowerPoint, ativando/desativando o áudio dos apresentadores e outras interrupções na reunião. 
    
- Marque a configuração **Desativar o áudio de todos os participantes** para assegurar que apenas os apresentadores possam transmitir áudio para a reunião.
    
- Verifique a **configuração de vídeo bloquear participantes** para garantir que apenas os apresentadores possam transmitir vídeo para a reunião.
    
### <a name="create-a-conferencing-policy"></a>Criar uma política de conferência

Crie uma nova política de conferência especificamente para grandes reuniões e atribua a política de conferência aos usuários que estão no pool dedicado a grandes reuniões. Defina a política de conferência usando as seguintes configurações:
  
- De definida **a opção MaxMeetingSize** como 1000. (O padrão é 250.)
    
- De definida **a opção AllowLargeMeetings** como **True**. 
    
- Definir a **opção EnableAppDesktopSharing** como **Nenhum**.
    
- Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.
    
- Definir a **opção AllowSharedNotes** como **False**.
    
- Definir a **opção AllowAnnotations** como **False**.
    
- Definir a **opção DisablePowerPointAnnotations** como **True**.
    
- Definir a **opção AllowMultiview** como **False**.
    
- Definir a **opção EnableMultiviewJoin** como **False**.
    
> [!NOTE]
> O suporte a grandes reuniões no Skype for Business Server exige que a **configuração AllowLargeMeetings** seja definida como true. Quando essa configuração for definida como verdadeira, a experiência do Skype for Business será otimizada para reuniões extra grande quando os usuários ingressarem na reunião. Especificamente, em uma grande reunião, o Skype for Business não mostrará a inicialização ou a atualização da lista completa de participantes da reunião, que é um gargalo de desempenho para o cliente e o Skype for Business Server. Em vez disso, o Skype for Business mostrará apenas informações sobre o usuário e a lista de apresentadores da reunião. O Skype for Business ainda mostrará o número total de participantes disponíveis nas grandes reuniões.

A **configuração AllowLargeMeetings $true** causa o seguinte:

- Oculta a lista de participantes. 

- Desabilita erros na janela de IM.

- Desabilita o vídeo de vários participantes.

- Desabilita a capacidade de promover um Participante para o Apresentador. Você deve planejar com antecedência e declarar todos os Apresentadores antes da reunião.

- Desabilita a capacidade de desativar participantes individuais.

- Desabilita a capacidade de aplicar o recurso Destaque de Vídeo de Bloqueio aos Participantes.

- Os usuários de discagem PSTN não poderão se desatar usando 6 porque a Assistência Virtual Pessoal, responsável pelos comandos DTMF em grandes reuniões ativas, está ausente.

- Se o apresentador/organizador agendar uma reunião na qual todos devem ser silenciados primeiro ("Silenciar Tudo"), os usuários PSTN serão silenciados durante toda a chamada e não poderão desativar o mudo por conta própria.

Com exceção da configuração de tamanho máximo da reunião, todas as outras configurações de política de conferência especificadas aqui são necessárias para desabilitar os recursos de conferência que não são necessários em grandes reuniões. 
  
Além disso, você precisa configurar o pool dedicado a grandes reuniões para que cada usuário do Skype for Business Server que está no pool e responsável por gerenciar o agendamento da reunião tenha as permissões apropriadas. Para tanto, siga estes passos:
  
- Definir a **opção Designar como apresentador** como **Nenhum**. Normalmente, um ou apenas alguns usuários de todos os participantes de uma grande reunião são apresentadores, portanto, os participantes não devem ser admitidos automaticamente em grandes reuniões como apresentadores. Em vez disso, os apresentadores devem ser explicitamente designados no horário de agendamento da reunião ou serem promovidos explicitamente durante uma grande reunião.
    
- Verifique se a caixa **de seleção Tipo de conferência Atribuído por** padrão não está selecionada. Essa configuração controla se o Complemento de Reunião Online do Skype for Business sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as reuniões agendadas têm a mesma URL de junção e informações de áudio. Em pequenos cenários de colaboração em grupo, ter um tipo de conferência atribuído funciona bem porque todos têm sua própria conferência atribuída individualmente, e a URL de entrada constante e as informações de áudio ajudam a facilitar a entrada mais rápida da reunião. No entanto, no cenário de grandes reuniões, a equipe de suporte a grandes reuniões agenda as grandes reuniões usando um único conjunto de credenciais de usuário e fornece URLs de junção e informações de áudio aos solicitantes da reunião. Nesse caso, usar uma URL diferente para ingressar em cada reunião funciona melhor.
    
- Verifique se a **caixa de seleção Admitir usuários anônimos** por padrão não está marcada, a menos que seja necessária. Essa configuração afeta o tipo de acesso à reunião padrão agendado pelo Complemento de Reunião Online do Skype for Business quando não estiver usando uma conferência atribuída. A opção apropriada para essa configuração depende das necessidades da sua organização. Se a maioria das grandes reuniões da sua organização for de reuniões internas, não selecione essa opção. Se a maioria das grandes reuniões exigir que usuários externos sejam capazes de ingressar, selecione essa opção.
    
Para obter mais informações sobre como criar uma política de conferência, consulte Gerenciar políticas [de conferência no Skype for Business Server.](../../manage/conferencing/conferencing-policies.md)
  

