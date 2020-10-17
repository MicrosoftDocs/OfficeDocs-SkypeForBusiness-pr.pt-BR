---
title: 'Lync Server 2013: o que há de novo para clientes'
description: 'Lync Server 2013: o que há de novo para clientes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90c1b93666b556c7ce7c4f3d94bea583dbf9b1a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546127"
---
# <a name="whats-new-for-clients-in-lync-server-2013"></a>O que há de novo para clientes no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-19_

O Microsoft Lync 2013 tem uma interface do usuário reprojetada e novos recursos importantes. Para os administradores, o cliente agora está incluído no programa de instalação do Office, fornecendo uma abordagem mais simplificada para a implantação do Office e personalização de clientes em sua organização.

<div>


> [!NOTE]  
> Para obter uma visão ilustrada das atualizações da interface de usuário do Lync 2013, consulte "What ' s New in Lync 2013" em <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A> .



</div>

<div>

## <a name="integration-with-office-setup"></a>Integração com a instalação do Office

O cliente Lync 2013 e o suplemento online Meeting para Lync 2013, que oferece suporte ao gerenciamento de reuniões a partir do cliente de mensagens e colaboração do Outlook, estão agora incluídos no programa de instalação do Office 2013.

Nas versões anteriores do Lync e do Office Communicator, você pode usar as propriedades do Windows Installer para personalizar e controlar a instalação do Office. Como o Lync 2013 está integrado à instalação do Office, você pode usar os seguintes métodos para personalizar a instalação do Lync 2013:

  - Usar a OCT (Ferramenta de Personalização do Office)

  - Usar o Config.xml para executar tarefas de instalação

  - Usar as opções de linha de comando de instalação

<div>


> [!NOTE]  
> O programa de instalação do Lync 2013 não desinstala versões anteriores do Lync ou Office Communicator. O cliente do Lync 2013 é instalado lado a lado com outros clientes do Lync ou do Office Communicator



</div>

Para obter detalhes, consulte [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Implantação da Política de Grupo

Como o Lync 2013 agora está incluído na instalação do Office, o método para implantar as configurações da política de grupo do Lync foi alterado. Nas versões anteriores do Lync e do Office Communicator, você poderia usar o Communicator. ADM para definir as configurações de política de grupo, enquanto no Lync 2013, agora você pode usar os modelos administrativos do Lync ADMX e ADML fornecidos junto com os modelos administrativos da política de grupo do Office.

Para obter detalhes, consulte [configurações de política de grupo para o Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Atualizações do suplemento de agendamento do Outlook

O suplemento reunião online do Lync 2013 inclui a personalização do convite de reunião e as novas opções de reunião.

  - Os administradores podem personalizar os convites de reunião da organização adicionando um logotipo personalizado, uma URL de suporte, uma URL do aviso de isenção legal ou um texto de rodapé personalizado. Para obter detalhes, consulte [Personalizando o suplemento de reunião online no Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Os novos controles de ativação de mudo para participantes permitem que os organizadores de reuniões agendem conferências ativando por padrão o mudo para o áudio e o vídeo dos participantes.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Plug-in de Virtual Desktop Infrastructure

O cliente Lync 2013 agora oferece suporte a áudio e vídeo em um ambiente de infraestrutura de área de trabalho virtual (VDI). Um usuário pode conectar um dispositivo de áudio ou vídeo (por exemplo, um fone de ouvido ou uma câmera) ao computador local (por exemplo, um computador cliente fino ou realocado). O usuário pode se conectar à máquina virtual, entrar no cliente do Lync 2013 que está sendo executado na máquina virtual e participar da comunicação de áudio e vídeo em tempo real, como se o cliente estivesse sendo executado localmente. Os recursos a seguir têm suporte em um ambiente de área de trabalho virtual:

  - Integração de dispositivos de áudio e vídeo, incluindo:
    
      - Controles de chamada do dispositivo
    
      - Integração de presença no dispositivo
    
      - Suporte á vários HIDs (dispositivos de interface humana)

  - Suporte a serviços de local e emergência.

  - Suporte para todas as modalidades do Lync, incluindo mensagens instantâneas, áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho, compartilhamento do PowerPoint, quadro de comunicações e transferência de arquivos.

  - Suporte a áudio e vídeo em chamadas entre duas pessoas e chamadas em conferência.

Para obter informações sobre a implantação do plug-in VDI, consulte [implantando o plug-in do LYNC VDI no Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Melhorias de vídeo

Vários novos recursos melhoram consideravelmente a experiência de vídeo dos participantes de conferências.

  - O vídeo foi aprimorado com detecção facial e enquadramento inteligente para que o vídeo do participante se desloque para mantê-lo centralizado no quadro.

  - Agora há suporte a vídeo de alta definição em chamadas entre duas pessoas e conferências com vários participantes. Os usuários podem visualizar resoluções de até 1080P HD.

  - Os participantes podem selecionar entre vários layouts de reunião: o Modo de Exibição de Galeria mostra as fotos e os vídeos de todos os participantes; o Modo de Exibição do Orador mostra o conteúdo da reunião e apenas a foto e o vídeo do orador atual; o Modo de Exibição de Apresentação mostra somente o conteúdo da reunião; e o Modo de Exibição Compacto mostra somente os controles da reunião.

  - Com o novo recurso de Galeria, os participantes podem ver várias transmissões de vídeo ao mesmo tempo. Se houver mais de cinco participantes na conferência, as transmissões de vídeo somente dos participantes mais ativos aparecerão na linha superior e as fotos dos outros participantes serão exibidas.

  - Os participantes podem usar o recurso de fixar vídeo para selecionar uma ou mais das transmissões de vídeo disponíveis para que fiquem sempre visíveis.

  - Os apresentadores podem usar o recurso Destaque de Vídeo para selecionar o vídeo de uma pessoa para que todos os participantes da reunião vejam somente esse participante.

</div>

<div>

## <a name="chat-room-integration"></a>Integração da sala de chat

O Lync 2013 agora integra os recursos anteriormente fornecidos pelo Lync 2010 Group Chat. Não há mais necessidade de um cliente de chat em grupo separado.

  - No Lync 2013, os usuários podem pesquisar salas de chat, adicionar salas de chat a seus contatos, monitorar a atividade de sala de chat e ler e postar mensagens.

  - Os usuários podem criar feeds de tópicos para serem notificados se algum participante de uma de suas salas de chat adicionar uma postagem que contenha palavras-chave específicas.

  - Com a nova página de opções **Chat Persistente**, os usuários podem definir sons e alertas de notificação que são acionados quando alguém posta mensagens em suas salas de chat.

</div>

<div>

## <a name="lync-web-app-updates"></a>Atualizações do Lync Web App

Lync Web App é o cliente de conferência baseado na Web para reuniões do Lync Server 2013. Nesta versão, a adição de áudio e vídeo do computador ao Lync Web App oferece uma experiência completa de reunião para qualquer pessoa que não tenha um cliente Lync instalado localmente. Os participantes da reunião têm acesso a todos os recursos de colaboração e compartilhamento e controles de reunião de apresentador.

Quando um usuário tenta ingressar em uma reunião, mas não tem um cliente instalado localmente, o Lync Web App é aberto. Se você deseja permitir opções adicionais para ingressar na reunião, é possível configurar a página de ingresso na reunião; consulte [Configurando a página de ingresso na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) na documentação de implantação.

Devido aos aprimoramentos do Lync Web App, uma versão atualizada do participante não está disponível para o Lync Server 2013. O Lync Web App é o cliente escolhido para participantes de fora da sua organização. Não é necessária a instalação local de um cliente, mas recursos de áudio, vídeo e compartilhamento exigem que um plug-in seja instalado na primeira utilização.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Lync 2013 para atualizações de clientes móveis

Além de recursos avançados de presença, contatos e mensagens instantâneas, os clientes móveis do Lync 2013 agora fornecem chamadas de voz e vídeo através da Internet e conexões de dados da rede celular. Com um único toque do link de reunião em um item de calendário, os usuários móveis podem ingressar em reuniões de vídeo e voz do Lync. Para obter mais informações sobre clientes móveis do Lync 2013, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Atualizações da interface de usuário do Lync 2013

<div>

## <a name="accessibility-updates"></a>Atualizações de acessibilidade

O Lync 2013 incorpora vários novos recursos de acessibilidade.

  - O Lync 2013 oferece suporte a alta resolução de DPI, permitindo que os usuários dimensionem texto e gráficos para 125% e 150% de pontos por polegada.

  - O Lync oferece suporte de alto contraste para que a interface do usuário permaneça totalmente funcional quando usada com temas de alto contraste no Windows.

  - O Lync oferece mais de 100 atalhos de teclado para que os usuários possam acessar funções importantes sem um mouse. Por exemplo, eles podem pressionar Alt+C para aceitar uma chamada ou Alt+I para ignorá-la sem precisar alternar ou definir o foco. A combinação de teclas Alt+Q encerra uma chamada, Ctrl+N inicia o OneNote e Alt+T abre o menu Ferramentas.

  - O amplo suporte ao leitor de tela no Lync 2013 garante que todas as notificações, solicitações de entrada e mensagens instantâneas sejam lidas em voz alta quando um leitor de tela estiver habilitado.

</div>

<div>

## <a name="presence-while-sharing"></a>Presença durante o compartilhamento

Quando o Lync detecta que um usuário está compartilhando, o Lync atribui automaticamente o usuário a apresentar o status de presença. Esse status bloqueia todas as comunicações de entrada, a menos que a relação de privacidade Grupo de Trabalho tenha sido atribuída ao remetente. Se o usuário estiver usando o recurso de compartilhamento totalmente em um monitor secundário, o Lync não atribuirá um status de presença de apresentação.

</div>

<div>

## <a name="conversation-window-updates"></a>Atualizações da janela Conversa

A janela Conversa reformulada oferece acesso mais rápido a recursos importantes.

  - Com o novo recurso de conversas com guias, os usuários agora podem manter todas as suas IMs e salas de chat em uma única janela Conversa. As guias na lateral esquerda da janela Conversa permite que os usuários naveguem facilmente entre todas as conversas ativas.

  - Os usuários podem destacar uma conversa individual em uma janela separada e redimensioná-la. Além disso, também podem reinserir a janela na janela Conversa principal.

  - O Lync 2013 reabre as conversas de um usuário quando o usuário se desconecta e entra novamente no Lync.

  - Os usuários podem rapidamente adicionar a qualquer conversa ferramentas de IM, vídeo, compartilhamento de programas, compartilhamento de área de trabalho ou webconferência (quadro de comunicações, notas de reunião, blocos de anotações compartilhados e anexos).

  - Em uma reunião em que vídeo ou conteúdo está sendo compartilhado, os usuários podem destacar o vídeo da reunião ou o conteúdo compartilhado em uma janela separada e redimensioná-la.

</div>

<div>

## <a name="lync-main-window-updates"></a>Atualizações da janela principal do Lync

A nova aparência simplificada mantém recursos conhecidos, como o campo de notas **O que está acontecendo hoje?**, o seletor de status e o seletor **Defina o local**.

  - Quando as salas de chat estão habilitadas, os usuários visualizam um novo ícone de **salas de chat** na página principal do Lync. Com o ícone **Salas de Chat**, eles podem rapidamente acessar suas salas de chat e filtros.

  - Os usuários podem clicar nos ícones de modo de exibição para alternar entre os modos **Contatos**, **Salas de Chat**, **Conversas** ou **Telefone**.

  - Se os usuários tiverem sido migrados para o Exchange 2013, poderão carregar uma imagem de alta resolução.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Atualizações do modo de exibição Contatos e do Cartão de Visita

O Lync 2013 oferece aos usuários maneiras diferentes de exibir contatos e grupos no modo de exibição de **contatos** .

  - Com o novo repositório unificado de contatos, depois que os contatos do Lync dos usuários são migrados para o Exchange 2013, os usuários podem acessar e gerenciar seus contatos do Lync 2013, Outlook ou Outlook Web App e seus favoritos permanecem sincronizados. Por exemplo, se um usuário adicionar um contato a favoritos no Outlook, o contato aparecerá no grupo favoritos no Lync 2013.

  - Se você tiver adicionado e configurado o proxy XMPP e o gateway XMPP, os usuários poderão adicionar contatos de parceiros XMPP para mensagens instantâneas e presença.

  - O novo recurso **Adicionar um contato que não é da minha organização** oferece aos usuários uma maneira fácil de adicionar pessoas de fora da organização.

  - O novo grupo **Favoritos** permite que os usuários criem uma lista de pessoas que contatam com mais frequência para agilizar o acesso.

  - Os usuários podem usar a nova página de opções **Lista de Contatos** para escolher como desejam classificar e exibir os contatos. Eles podem selecionar um modo de exibição expandido de duas linhas, que mostra as fotos dos contatos, ou um modo de exibição compacto de uma única linha. Os usuários também podem classificar os contatos por ordem alfabética ou por disponibilidade.

</div>

<div>

## <a name="conferencing-updates"></a>Atualizações de conferências

O Lync 2013 oferece vários aprimoramentos aos recursos de conferência.

  - Dependendo do tipo de reunião, os usuários agora podem ativar o mudo para os participantes e permitir ou bloquear o compartilhamento de vídeo ao agendarem a reunião. Essas opções estão disponíveis na página **Opções de Reunião** e são recomendadas para reuniões grandes com mais de 20 participantes.

  - Controles de áudio fáceis de usar na sala de reunião permitem que o usuário controle as opções de áudio, como ativar mudo, desativar mudo, alterar dispositivo etc.

  - Ao compartilhar programas, os usuários podem selecionar vários programas para compartilhamento se precisarem trabalhar com mais de um ao mesmo tempo.

  - Os usuários agora podem carregar apresentações que contêm clipes de vídeo carregando o arquivo do PowerPoint e apontando o mouse sobre o slide para exibir os controles de vídeo, como reproduzir e pausar, bem como os controles de áudio.

  - Durante uma reunião, os usuários podem incorporar outra conversa aberta à reunião usando o comando **Mesclar esta Conversa em** no menu **Mais Opções** (**…**).

  - Para ver os nomes dos participantes, os usuários podem passar o mouse sobre o botão **Exibir Participantes** ou clicar em **Mostrar Lista de Participantes** para encaixar o painel na reunião.

  - Dependendo do tipo de reunião, os usuários podem selecionar entre vários modos de exibição de participantes e conteúdo.

  - As gravações de reuniões são automaticamente salvas em um formato que pode ser reproduzido no Windows Media Player (MP4). Os usuários podem facilmente compartilhar o arquivo com qualquer pessoa ou usar o recurso **Publicar** do gerenciador de gravações para postar a gravação em um local compartilhado.

  - O OneNote permite novas maneiras de colaborar em uma reunião. Durante uma reunião, os usuários podem fazer anotações com o OneNote para uso pessoal após a reunião ou usar os blocos de anotações compartilhados e realizar edições em conjunto com os participantes da reunião em tempo real. Todos os membros da equipe podem acessar as anotações compartilhadas para contribuir com informações, desenvolver ideias ou usar as páginas do bloco de anotações como um quadro de comunicações virtual. As pessoas e o conteúdo compartilhado na reunião são automaticamente adicionados às anotações.

  - Os usuários podem alternar entre os tipos de conteúdo usando a opção **Compartilhar conteúdo e liderar atividades da reunião** na parte inferior da sala de reunião. Eles também podem usar o menu **Gerenciar Conteúdo Apresentável** para escolher qual conteúdo desejam compartilhar.

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de clientes no Lync Server 2013](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

