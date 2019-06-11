---
title: 'Lync Server 2013: Novidades para clientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf37f68d0ea11e17a799956f285d8ca82eb2a27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Novidades para clientes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-19_

O Microsoft Lync 2013 tem uma interface de usuário reprojetada e novos recursos importantes. Para administradores, o cliente agora está incluído no programa de instalação do Office, fornecendo uma abordagem mais simplificada para implantar o Office e personalizar clientes em sua organização.

<div>


> [!NOTE]  
> Para ver uma exibição ilustrada das atualizações da interface do usuário do Lync 2013, consulte "novidades do Lync <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>2013" em.



</div>

<div>

## <a name="integration-with-office-setup"></a>Integração com a instalação do Office

O cliente do Lync 2013 e o suplemento de reunião online do Lync 2013, que dá suporte ao gerenciamento de reuniões, dentro do cliente de mensagens e colaboração do Outlook, agora estão incluídos no programa de instalação do Office 2013.

Em versões anteriores do Lync e do Office Communicator, você pode usar as propriedades do Windows Installer para personalizar e controlar a instalação do Office. Como o Lync 2013 está integrado à instalação do Office, você pode usar os seguintes métodos para personalizar a configuração do Lync 2013:

  - Usar a OCT (Ferramenta de Personalização do Office)

  - Use o config. xml para executar tarefas de instalação

  - Usar opções de linha de comando de configuração

<div>


> [!NOTE]  
> O programa de instalação do Lync 2013 não desinstala versões anteriores do Lync ou do Office Communicator. O cliente do Lync 2013 é instalado lado a lado com outros clientes do Lync ou do Office Communicator



</div>

Para obter detalhes, consulte Implantando [clientes do Lync no Lync Server 2013](lync-server-2013-deploying-lync-clients.md).

</div>

<div>

## <a name="group-policy-deployment"></a>Implantação de política de grupo

Como o Lync 2013 agora está incluído no programa de instalação do Office, o método de implantação das configurações da política de grupo do Lync foi alterado. Em versões anteriores do Lync e do Office Communicator, você pode usar o Communicator. ADM para definir configurações de política de grupo, enquanto no Lync 2013 agora você pode usar os modelos administrativos do Lync e do ADML fornecidos juntamente com a política de grupo do Office Modelos administrativos.

Para obter detalhes, consulte [configurações de política de grupo para o Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Atualizações do suplemento agendamento do Outlook

O suplemento reunião online do Lync 2013 inclui a personalização de convites de reunião e as novas opções de reunião.

  - Os administradores podem personalizar os convites para reunião da organização adicionando um logotipo personalizado, uma URL de suporte, uma URL de isenção de responsabilidade legal ou texto de rodapé personalizado. Para obter detalhes, consulte [Personalizando o suplemento de reunião online no Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).

  - Novos controles de mudo para participantes permitir que os organizadores da reunião agendem conferências que tenham áudio e vídeo de participantes com mudo ativado por padrão.

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>Plug-in de infraestrutura de área de trabalho virtual

O cliente Lync 2013 agora dá suporte a áudio e vídeo em um ambiente VDI (infraestrutura de área de trabalho virtual). Um usuário pode conectar um dispositivo de áudio ou de vídeo (por exemplo, um fone de ouvido com microfone ou uma câmera) ao computador local (por exemplo, um cliente leve ou um computador redefinido). O usuário pode se conectar à máquina virtual, entrar no cliente do Lync 2013 que está em execução na máquina virtual e participar de comunicações de áudio e vídeo em tempo real, como se o cliente estivesse em execução localmente. Os recursos a seguir são suportados em um ambiente de área de trabalho virtual:

  - Integração de dispositivos para áudio e vídeo, incluindo o seguinte:
    
      - Controles de chamada do dispositivo
    
      - Integração de presença no dispositivo
    
      - Suporte a vários HID (dispositivo de interface humana)

  - Suporte a locais e serviços de emergência.

  - Suporte para todas as modalidades do Lync, incluindo mensagens instantâneas, áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho, compartilhamento do PowerPoint, quadro de comunicações e transferência de arquivos.

  - Suporte a áudio e vídeo em chamadas de pessoa para pessoa e chamadas em conferência.

Para obter informações sobre a implantação do plug-in VDI, consulte [implantação do plug-in VDI do Lync no Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).

</div>

<div>

## <a name="video-enhancements"></a>Melhorias de vídeo

Vários novos recursos melhoram significativamente a experiência com vídeo para participantes de conferências.

  - Vídeo aprimorado com detecção de rosto e enquadramento inteligente, para que o vídeo de um participante se movimente para ajudar a mantê-los centralizados no quadro.

  - O vídeo de alta definição agora é compatível com chamadas de dois participantes e conferências de vários participantes. Os usuários podem experimentar resoluções de até HD 1080P.

  - Os participantes podem selecionar um layout de reunião diferente: o modo de exibição de galeria mostra as imagens ou vídeos dos participantes; O modo de exibição do orador mostra o conteúdo da reunião e somente o vídeo ou a imagem atual do orador; Modo de exibição de apresentação mostra o conteúdo da reunião somente; O modo de exibição compacto mostra apenas os controles da reunião.

  - Com o novo recurso de galeria, os participantes podem ver várias alimentações de vídeo ao mesmo tempo. Se a conferência tiver mais de cinco participantes, as alimentações de vídeo apenas dos participantes ativos serão exibidos na linha superior e as imagens serão exibidas para os outros participantes.

  - Os participantes podem usar a fixação de vídeo para selecionar um ou mais dos feeds de vídeo disponíveis para ficarem visíveis o tempo todo.

  - Os apresentadores podem usar o recurso de Spotlight em vídeo para selecionar o feed de vídeo de uma pessoa para que todos os participantes da reunião vejam apenas esse participante.

</div>

<div>

## <a name="chat-room-integration"></a>Integração da sala de chat

O Lync 2013 agora integra os recursos fornecidos anteriormente pelo Lync 2010 Group Chat. Um cliente de chat em grupo separado não é mais necessário.

  - De dentro do Lync 2013, os usuários podem procurar salas de chat, adicionar salas de chat a seus contatos, monitorar a atividade de salas de chat e ler e postar mensagens.

  - Os usuários podem criar feeds de tópico para que sejam notificados se alguém em uma das salas de chat adicionar uma postagem contendo palavras-chave específicas.

  - Com a nova página de opções de **chat persistente** , os usuários podem definir alertas de notificação e sons que se aplicam quando as pessoas publicam mensagens em suas salas de chat.

</div>

<div>

## <a name="lync-web-app-updates"></a>Atualizações do Lync Web App

O Lync Web App é o cliente de conferência baseado na Web para reuniões do Lync Server 2013. Nesta versão, a adição de áudio e vídeo do computador ao Lync Web App oferece uma experiência completa na reunião para qualquer pessoa que não tenha um cliente do Lync instalado localmente. Os participantes de reunião têm acesso a todos os recursos de colaboração e compartilhamento e aos controles de reunião do apresentador.

Quando um usuário tenta ingressar em uma reunião, mas não tem um cliente instalado localmente, o Lync Web App é aberto. Se quiser permitir opções adicionais para ingressar na reunião, você pode configurar a página ingressar na reunião; consulte [Configurando a página ingressar na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) na documentação de implantação.

Devido aos aprimoramentos do Lync Web App, uma versão atualizada do participante não está disponível para o Lync Server 2013. O Lync Web App é o cliente escolhido para participantes de fora da sua organização. Não é necessária nenhuma instalação de cliente local, embora os recursos de áudio, vídeo e compartilhamento exijam que um plug-in seja instalado na primeira utilização.

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Lync 2013 para atualizações de clientes móveis

Além de recursos avançados de presença, contatos e mensagens instantâneas, agora os clientes móveis do Lync 2013 fornecem chamadas de voz e vídeo pela Internet e conexões de dados da rede celular. Com um único toque do link da reunião em um item de calendário, os usuários móveis podem ingressar em reuniões com voz e vídeo do Lync. Para obter mais informações sobre clientes móveis do Lync 2013, consulte [planejando para clientes móveis no Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Atualizações da interface do usuário do Lync 2013

<div>

## <a name="accessibility-updates"></a>Atualizações de acessibilidade

O Lync 2013 incorpora vários novos recursos de acessibilidade.

  - O Lync 2013 suporta resolução de alta DPI, permitindo que os usuários dimensionem o texto e os elementos gráficos para 125% e 150% de pontos por polegada.

  - O Lync fornece suporte de alto contraste para que a interface do usuário permaneça totalmente funcional quando usada com temas de alto contraste no Windows.

  - O Lync oferece mais de 100 atalhos de teclado para que os usuários possam acessar funções importantes sem um mouse. Por exemplo, os usuários podem pressionar Alt + C para aceitar uma chamada ou ALT + I para ignorá-la, sem precisar fazer a Tabulação ou definir o foco. Pressionar (ALT + Q) Finaliza uma chamada, (Ctrl + N) inicia o OneNote e (Alt + T) abre o menu ferramentas.

  - O suporte a leitor de tela extensivo no Lync 2013 garante que todas as notificações, solicitações de entrada e mensagens instantâneas sejam lidas em voz alta quando um leitor de tela estiver habilitado.

</div>

<div>

## <a name="presence-while-sharing"></a>Presença durante o compartilhamento

Quando o Lync detecta que um usuário está compartilhando, o Lync atribui automaticamente ao usuário um status de presença apresentando. Esse status bloqueia todas as comunicações de entrada, a menos que o remetente tenha atribuído a relação de privacidade do grupo de trabalho. Se o usuário estiver usando o recurso de compartilhamento totalmente em um monitor secundário, o Lync não atribuirá um status de presença de apresentação.

</div>

<div>

## <a name="conversation-window-updates"></a>Atualizações da janela de conversa

A janela de conversa reformulada fornece acesso mais rápido a recursos importantes.

  - Com o novo recurso conversas com guias, os usuários agora podem manter todas as salas de chat e chats em uma janela de conversa. As guias no lado esquerdo da janela de conversa permitem que os usuários naveguem facilmente entre todas as conversas ativas.

  - Os usuários podem mostrar uma conversa individual em uma janela separada e, em seguida, redimensionar a janela. Eles também podem retornar a janela de volta à janela de conversa principal.

  - O Lync 2013 reabre as conversas de um usuário quando o usuário se desconecta e entra novamente no Lync.

  - Os usuários podem adicionar rapidamente mensagens instantâneas, vídeo, compartilhamento de programas, compartilhamento de área de trabalho ou ferramentas de Webconferência (quadro de comunicações, anotações da reunião, blocos de anotações compartilhados e anexos) a qualquer conversa.

  - Em uma reunião na qual um vídeo ou conteúdo está sendo compartilhado, os usuários podem exibir o vídeo da reunião ou o conteúdo compartilhado e, em seguida, redimensionar a janela.

</div>

<div>

## <a name="lync-main-window-updates"></a>Atualizações da janela principal do Lync

A nova aparência simplificada retém recursos conhecidos, como o **que está acontecendo hoje?** , o seletor de status e o seletor de **local definir seu local** .

  - Quando salas de chat estiverem habilitadas, os usuários verão um novo ícone de **salas de chat** na página principal do Lync. Com o ícone de **salas de chat** , os usuários podem acessar rapidamente seus respectivos filtros e salas de chat.

  - Os usuários podem clicar nos ícones de exibição para alternar para o modo de exibição **contatos** , o modo de exibição **salas de chat** , o modo de exibição **conversas** ou o modo de exibição **telefone**

  - Se os usuários foram migrados para o Exchange 2013, eles podem carregar uma imagem de alta resolução.

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>Modo de exibição contatos e atualizações de cartão de contato

O Lync 2013 oferece aos usuários diferentes maneiras de exibir contatos e grupos no modo de exibição **contatos** .

  - Com o novo repositório de contatos unificado, após a migração dos contatos do Lync dos usuários para o Exchange 2013, os usuários podem acessar e gerenciar seus contatos no Lync 2013, no Outlook ou no Outlook Web App, e seus favoritos ficam sincronizados. Por exemplo, se um usuário adicionar um contato aos favoritos no Outlook, o contato aparecerá no grupo favoritos no Lync 2013.

  - Se você adicionou e configurou o proxy XMPP e o Gateway XMPP, os usuários podem adicionar contatos de parceiros baseados no XMPP para mensagens instantâneas e presença.

  - Um novo recurso **Adicionar um contato que não está em minha organização** proporciona aos usuários uma maneira fácil de adicionar pessoas de fora da organização.

  - Um novo grupo **favoritos** permite que os usuários criem uma lista de pessoas que os usuários contatam com mais frequência para obter um acesso mais rápido.

  - Os usuários podem usar a nova página Opções da **lista de contatos** para escolher como os usuários desejam classificar e exibir contatos. Os usuários podem selecionar uma exibição expandida de duas linhas que mostre as imagens dos contatos ou uma exibição condensada de uma linha. Os usuários também podem classificar os contatos em ordem alfabética ou por disponibilidade.

</div>

<div>

## <a name="conferencing-updates"></a>Atualizações de conferência

O Lync 2013 oferece vários aprimoramentos em recursos de conferência.

  - Dependendo do tipo de reunião, os usuários podem agora ativar o mudo da audiência e permitir ou bloquear o compartilhamento de vídeo ao agendar a reunião. Essas opções estão disponíveis na página **Opções de reunião** e são recomendadas para reuniões grandes com mais de 20 participantes.

  - Os controles de áudio fáceis de usar na sala de reuniões permitem que o usuário controle opções de áudio, como ativar mudo, desativar mudo, alterar dispositivo e assim por diante.

  - Ao compartilhar programas, os usuários podem selecionar vários programas para compartilhar se precisarem trabalhar com mais de um programa.

  - Agora os usuários podem carregar apresentações que contenham clipes de vídeo carregando o arquivo do PowerPoint e apontando o mouse sobre o slide para exibir controles de vídeo, como controles de reprodução, pausa e áudio.

  - Durante uma reunião, os usuários podem mesclar outra conversa aberta na reunião usando **mesclar esta chamada** no menu **mais opções** (**...**).

  - Para ver os nomes dos participantes, os usuários podem focalizar o mouse sobre o botão **Exibir participantes** ou clicar em **Mostrar lista de participantes** para encaixar o painel na reunião.

  - Dependendo do tipo de reunião, os usuários podem selecionar entre vários modos de exibição de conteúdo e de participantes diferentes.

  - As gravações de reunião são salvas automaticamente em um formato que é reproduzido no Windows Media Player (MP4). Os usuários podem compartilhar facilmente o arquivo com qualquer pessoa ou usar o recurso **publicar** no Gerenciador de gravação para postar a gravação em um local compartilhado.

  - O OneNote permite novas maneiras de colaborar em uma reunião. Durante uma reunião, os usuários podem fazer anotações com o OneNote para uso pessoal após a reunião ou usar blocos de anotações compartilhados e coedição com participantes da reunião em tempo real. Todos os membros da equipe podem acessar as anotações compartilhadas em informações do Contribute, ideias ou usar as páginas do bloco de anotações como um quadro de comunicações virtual. As pessoas e o conteúdo compartilhado na reunião são adicionados automaticamente às anotações.

  - Os usuários podem alternar entre tipos de conteúdo usando o **recurso compartilhar conteúdo e conduzir atividades da reunião** na parte inferior da sala de reunião. Os usuários também podem usar o menu **gerenciar conteúdo apresentável** para escolher o conteúdo que deseja compartilhar.

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

