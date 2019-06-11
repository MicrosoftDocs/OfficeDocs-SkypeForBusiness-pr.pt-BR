---
title: 'Lync Server 2013: como funciona o servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf6179e1ce24264c2079b3096fa9bb8c539ca1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Como o servidor de chat persistente funciona no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-21_

Lync Server 2013, servidor de chat persistente permite que você participe de conversas com vários participantes, com base em tópicos que persistem ao longo do tempo. O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:

  - Melhorar a comunicação entre equipes geograficamente dispersas e de várias funções

  - Amplie o reconhecimento e a participação em informações

  - Melhorar a comunicação com a sua organização estendida

  - Reduzir a sobrecarga de informações

  - Melhorar o reconhecimento de informações

  - Aumentar a dispersão de informações e conhecimento importantes

Você pode implantar o servidor de chat persistente como uma função opcional no Lync Server 2013. Os serviços de chat persistente são executados em um pool dedicado e um pool de servidores de chat persistentes depende de um pool de servidores do Lync para direcionar mensagens para ele. Os clientes usam a comunicação de chat extensível via SIP (XCCOS). Os servidores de front-end do Lync Server são configurados para direcionar o tráfego para um pool de servidores de chat persistente.

<div>

## <a name="high-level-architecture"></a>Arquitetura de alto nível

Os diagramas a seguir fornecem perspectivas de alto nível da arquitetura e dos serviços do servidor de chat persistente.

**Arquitetura de alto nível do servidor de chat persistente**

![Arquitetura de servidor de chat persistente.] (images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitetura de servidor de chat persistente.")

**Serviços de alto nível do servidor de chat persistente**

![Componentes persistentes do servidor de chat.] (images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes persistentes do servidor de chat.")

Dois serviços são executados nos servidores de front-end do servidor de chat persistente:

  - Chat persistente (canal)

  - Conformidade

<div>

## <a name="persistent-chat-channel-service"></a>Serviço de chat (canal) persistente

O serviço de chat (canal) persistente é o serviço principal responsável pelo servidor de chat persistente. Esse serviço oferece as seguintes funções:

  - Aceita as mensagens recebidas

  - Registra e lista os participantes em uma sala do Chat Persistente

  - Retransmite mensagens a outros assinantes do canal

  - Implementa a lógica para o gerenciamento de canal, o convite da sala de chat, a pesquisa e novas notificações de conteúdo

O serviço de chat (canal) persistente armazena e acessa o conteúdo da sala de chat e outros metadados do sistema (regras de autorização e assim por diante) usando o repositório de chat persistente. Esse serviço armazena arquivos que são carregados em salas de chat no repositório de arquivos de chat persistente.

</div>

<div>

## <a name="compliance-service"></a>Serviço de conformidade

O serviço de conformidade é um componente opcional do servidor de chat persistente e é responsável por arquivar conteúdo e eventos de chat no repositório de conformidade de chat persistente. Se a sua organização tiver regulamentos que exigem que a atividade de Chat Persistente seja arquivada, você pode implantar o serviço opcional de Conformidade de Chat Persistente. O serviço de conformidade está instalado em cada servidor de chat persistente em um pool de chat persistente. Quando configurado, a conformidade do servidor de chat persistente registra atividades do usuário, como ingressar e sair de salas, e postar e ler mensagens. O serviço de conformidade armazena arquivos que precisam ser arquivados no repositório de arquivos de conformidade de chat persistente.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Serviços Web de chat persistente

Nos servidores de front-end do Lync Server, dois serviços executados dependem dos serviços de informações da Internet (IIS) e são implementados como componentes Web:

  - **Serviços Web de chat persistentes para carregamento/download de arquivo** Responsável por publicar e recuperar arquivos de salas de chat.

  - **Serviços Web persistentes de chat para gerenciamento de salas de chat** Responsável por fornecer aos usuários a capacidade de gerenciar salas de chat e criar novas salas de chat.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>Como começo a usar o servidor de chat persistente?

O servidor de chat persistente é uma função de servidor opcional na infraestrutura do Lync Server 2013. Se você instalar a função de servidor de chat persistente, todos os usuários que foram habilitados por meio da política por um administrador poderão usar o chat persistente com o cliente Lync 2013.

Para obter detalhes sobre como implantar o servidor de chat persistente e habilitar os usuários a aproveitar os recursos por política, consulte Implantando o [servidor de chat persistente no Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Para obter detalhes sobre como definir as configurações na sua implantação do servidor de chat persistente, consulte Implantando o [servidor de chat persistente no Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e gerenciando o [Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).

Para obter detalhes sobre como habilitar os usuários por política, para que eles possam aproveitar a funcionalidade de chat persistente no cliente do Lync 2013, consulte [implantação do servidor de chat persistente no Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Gerenciamento do Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).

Se você implantou a conformidade persistente com o chat, consulte Gerenciando o [Lync server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md) para obter detalhes sobre como definir as configurações de conformidade.

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Fluxos de chamadas de chat persistentes

O cliente de chat persistente se comunica com o serviço de chat persistente usando XCCOS. As seqüências a seguir descrevem o processo de entrada e um cenário típico de assinatura de sala e mensagem de postagem de mensagem.

<div>

## <a name="sign-in"></a>Entrada

As etapas e o diagrama de fluxo de chamadas a seguir descrevem o processo de entrada.

**Fluxo de chamadas de entrada do cliente de chat persistente**

![Diagrama de fluxo de chamadas de servidor de chat persistente.] (images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagrama de fluxo de chamadas de servidor de chat persistente.")

1.  O cliente de chat persistente primeiro envia uma assinatura SIP para recuperar o documento de provisionamento em banda do servidor. Este documento indica se o chat persistente está habilitado ou desabilitado para o usuário e a lista de URIs SIP do pool do servidor de chat persistente.

2.  O cliente de chat persistente envia uma mensagem de convite SIP para o URI SIP do servidor de chat persistente que obteve na etapa anterior. A sequência de convite é seguida por 200 OK e ACK, e o cliente de chat persistente agora abriu uma sessão SIP com um ponto de extremidade de servidor de chat persistente. Consequentemente, o cliente de chat persistente se comunica com o servidor de chat persistente enviando mensagens de informações SIP que contêm mensagens de chat ou comandos solicitando que o servidor execute uma ação. Todas essas mensagens são confirmadas com o serviço do 200 OK ou do 503 indisponível (ou seja, no caso de carga excessiva do servidor). Se o cliente receber uma resposta 503, ele tentará novamente a mensagem. (Este exemplo não inclui uma resposta 503.) Se o servidor aceitar a mensagem ou o comando e enviar 200 OK, ele fornecerá uma resposta para o cliente na forma de uma mensagem de informações SIP separada. Esta resposta inclui uma referência para o comando de origem.

3.  O cliente de chat persistente envia uma mensagem SIP INFO que contém o comando XCCOS **GetServerInfo** . O servidor de chat persistente responde com uma nova mensagem de informações SIP que contém informações sobre a configuração do serviço de chat persistente.

4.  O cliente de chat persistente envia uma mensagem SIP INFO que contém o **** comando XCCOS getassociations. O servidor de chat persistente responde com uma nova mensagem de informações SIP que contém a lista de salas dos quais o usuário é membro. O cliente de chat persistente repete o comando para recuperar a lista de salas das quais o usuário é um gerente.

5.  O cliente de chat persistente Obtém a lista de salas seguidas do documento "presença", em que cada sala acompanhada é representada por uma categoria "roomSetting". Todas as salas seguidas são unidas por uma única mensagem SIP que contém o comando XCCOS **bPara participar** que contém a lista de URIs de sala. Como a lista de salas seguidas é mantida no servidor, qualquer cliente em qualquer computador tem a mesma lista de salas seguidas para o URI de usuário especificado. O cliente de chat persistente também mantém a lista de salas abertas (se esta opção estiver habilitada pelo usuário) no registro do computador local e ingressar em cada uma dessas salas na entrada, enviando uma mensagem SIP INFO que contém o comando XCCOS **Join** para cada sala aberta . Como essa lista é mantida no registro, ela pode ser diferente em dois clientes de chat persistentes em execução em computadores diferentes.

6.  Para cada sala unida, o cliente de chat persistente envia uma mensagem de informações SIP que contém o comando XCCOS **bccontext** . O servidor de chat persistente responde com uma nova mensagem de informações SIP que contém a mensagem de chat mais recente na sala.

7.  O cliente de chat persistente envia uma mensagem SIP INFO que contém um comando XCCOS **getinv** (ou seja, Get convite) para solicitar novos convites de sala que o cliente ainda não viu. Em uma mensagem de informações SIP separada, o servidor de chat persistente retorna uma lista dessas salas.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>Assinar uma sala e postar uma mensagem

As etapas e o diagrama de fluxo de chamadas a seguir descrevem um cenário típico de assinatura de sala e de postagem de mensagem.

**Assinatura da sala de chat persistente do cliente de chat e fluxo de chamadas de lançamento de mensagens**

![Licença da sala e cenário de postagem de mensagem.] (images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Licença da sala e cenário de postagem de mensagem.")

1.  No cliente de chat persistente, o Usuário1 clica em ingressar em **uma sala de chat**, clica em **Pesquisar**e, em seguida, insere critérios de pesquisa. O cliente de chat persistente envia uma mensagem SIP INFO que contém o comando XCCOS **chansrch** (localização da sala), juntamente com os critérios de pesquisa. O servidor de chat persistente consulta o banco de dados back-end e responde em uma nova mensagem de informações SIP que contém uma lista de salas disponíveis que atendem aos critérios de pesquisa.

2.  Usuário1 seleciona a sala de chat que deseja participar e, em seguida, clica em **acompanhar esta sala**. O cliente de chat persistente envia uma mensagem de informações SIP do servidor de chat persistente que contém o comando XCCOS **Join** e a ID da sala da sala de chat que o usuário selecionou. O servidor de chat persistente responde com uma mensagem de informações SIP que contém os dados de provisionamento.

3.  O cliente de chat persistente envia uma mensagem de informação SIP a um servidor de chat persistente que contém o comando XCCOS **bccontext** (contexto de chat). O servidor de chat persistente recupera o histórico de chats e retorna-o ao cliente de chat persistente em uma mensagem de informações SIP separada. Nesse ponto, o usuário entra na sala de chat e está pronto para participar.

4.  Usuário1 insere uma nova mensagem e, em seguida, clica em **Enviar**. O cliente de chat persistente envia a mensagem para a sala de chat em um comando XCCOS **grpchat** do SIP info. O servidor de chat persistente armazena uma cópia dessa nova mensagem no banco de dados de back-end de chat persistente.

5.  Servidor de chat persistente envia uma cópia separada da mensagem XCCOS **grpchat** do SIP info para Usuário2, que já entrou na sala de chat.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Fluxos de chamadas de conformidade de chat persistente

O servidor de chat persistente usa o serviço de enfileiramento de mensagens (também conhecido como MSMQ) e um banco de dados de conformidade adicional (mgccomp) para processar dados de conformidade. Como um exemplo de como os eventos de conformidade são processados, a sequência de eventos a seguir descreve como um evento de postagem de mensagem é processado.

1.  Um usuário publica uma mensagem em uma sala.

2.  O servidor de chat persistente coloca as informações pertinentes ao evento em uma fila particular do enfileiramento de mensagens.

3.  O servidor de conformidade de chat persistente lê esse evento da fila e o coloca no banco de dados do mgccomp para processamento posterior.

4.  Periodicamente, o servidor de conformidade de chat persistente processa um conjunto de eventos no banco de dados e envia-o ao adaptador de conformidade de chat persistente para processamento.

5.  Se o adaptador processar com êxito os dados, o servidor de conformidade de chat persistente excluirá os eventos do banco de dados do mgccomp.

</div>

</div>

<span> </span>

</div>

</div>

</div>

