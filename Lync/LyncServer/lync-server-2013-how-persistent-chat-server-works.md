---
title: 'Lync Server 2013: como funciona o servidor de chat persistente'
description: 'Lync Server 2013: como funciona o servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65df6a13305f75a8a25b85a39688fadf64e476c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562957"
---
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Como funciona o servidor de chat persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-21_

Lync Server 2013, servidor de chat persistente permite que você participe de conversas com vários tópicos, com base em tópico que persistem ao longo do tempo. O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:

  - Melhorar a comunicação entre equipes geograficamente distante e multifuncionais

  - Ampliar a conscientização e participação da informação

  - Melhorar a comunicação com sua organização estendida

  - Reduzir sobrecarga informacional

  - Melhorar a conscientização da informação

  - Melhorar a dispersão de informações e conhecimentos importantes

Você pode implantar o servidor de chat persistente como uma função opcional com o Lync Server 2013. Os serviços de chat persistente são executados em um pool dedicado, e um pool de servidor de chat persistente depende de um pool do Lync Server para encaminhar mensagens para ele. Os clientes utilizam eXtensible Chat Communication Over SIP (XCCOS). Os servidores front-end do Lync Server são configurados para rotear o tráfego para um pool de servidor de chat persistente.

<div>

## <a name="high-level-architecture"></a>Arquitetura de alto nível

Os diagramas a seguir fornecem perspectivas de alto nível da arquitetura e dos serviços do servidor de chat persistente.

**Arquitetura de alto nível de servidor de bate-papo persistente**

![Arquitetura do servidor de chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitetura do servidor de chat persistente.")

**Serviços de alto nível de servidor de bate-papo persistente**

![Componentes do servidor de chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes do servidor de chat persistente.")

Dois serviços são executados nos servidores de front-end do servidor de chat persistente:

  - Bate-papo persistente (canal)

  - Conformidade

<div>

## <a name="persistent-chat-channel-service"></a>Serviço de bate-papo (canal) persistente

O serviço de chat persistente (canal) é o principal serviço responsável pelo servidor de chat persistente. Este serviço fornece as seguintes funções:

  - Aceita as mensagens recebidas

  - Registra e lista os participantes online em uma sala de chat persistente

  - Retransmite mensagens a outros assinantes do canal

  - Implementa lógica para gerenciamento de canal, convite para sala de bate-papo, busca e notificações de novo conteúdo

O serviço de chat persistente (canal) armazena e acessa o conteúdo da sala de chat e outros metadados do sistema (regras de autorização e assim por diante) usando o repositório de chat persistente. Este serviço armazena arquivos que são carregados em salas de chat no repositório de arquivos de chat persistente.

</div>

<div>

## <a name="compliance-service"></a>Serviços de conformidade

O serviço de conformidade é um componente opcional do servidor de chat persistente e é responsável por arquivar conteúdo e eventos de chat no repositório de conformidade de chat persistente. Se sua organização tem regulamentações que exigem atividade de chat persistente para serem arquivadas, você pode implantar o serviço de conformidade de chat persistente opcional. O serviço de conformidade é instalado em cada servidor de chat persistente em um pool de chat persistente. Quando configurado, a conformidade do servidor de chat persistente registra as atividades do usuário, como ingressar e sair de salas, e postar e ler mensagens. O serviço de conformidade armazena arquivos que precisam ser arquivados no repositório de arquivos de conformidade de chat persistente.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Serviços Web de chat persistente

Nos servidores front-end do Lync Server, dois serviços são executados que dependem do IIS (serviços de informações da Internet) e são implementados como componentes da Web:

  - **Serviços Web de chat persistente para upload/download de arquivo** Responsável por postar e recuperar arquivos de salas de chat.

  - **Serviços Web de chat persistente para gerenciamento de salas de chat** Responsável por fornecer aos usuários a capacidade de gerenciar suas salas de chat e criar novas salas de chat.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>Como começar a usar o servidor de chat persistente?

O servidor de chat persistente é uma função de servidor opcional na infraestrutura do Lync Server 2013. Se você instalar a função de servidor de chat persistente, todos os usuários que tenham sido habilitados por meio da política por um administrador poderão usar o chat persistente com o cliente Lync 2013.

Para obter detalhes sobre como implantar o servidor de chat persistente e permitir que os usuários aproveitem os recursos por política, consulte [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Para obter detalhes sobre como definir as configurações na implantação do servidor de chat persistente, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Managing Lync Server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md).

Para obter detalhes sobre como habilitar usuários por política, de forma que eles possam aproveitar a funcionalidade de chat persistente no cliente Lync 2013, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Managing Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).

Se você implantou a conformidade de chat persistente, consulte [Managing Lync server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md) para obter detalhes sobre como definir as configurações de conformidade.

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Fluxos de chamadas de chat persistente

O cliente de chat persistente se comunica com o serviço de chat persistente usando o XCCOS. A sequência a seguir descreve o processo de inscrição e assinatura de sala típica e cenário de postagem de mensagem..

<div>

## <a name="sign-in"></a>Entrar

As etapas e o diagrama de fluxo de chamadas a seguir descrevem o processo de entrada.

**Fluxo de chamadas de entrada de cliente de chat persistente**

![Diagrama de fluxo de chamadas do servidor de chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagrama de fluxo de chamadas do servidor de chat persistente.")

1.  O cliente de chat persistente primeiro envia um SIP INSCREVEr-se para recuperar o documento de provisionamento em banda do servidor. Este documento indica se o chat persistente está habilitado ou desabilitado para o usuário e a lista de URIs SIP para o pool do servidor de chat persistente.

2.  O cliente de chat persistente envia uma mensagem de convite SIP para o URI SIP do servidor de chat persistente obtido na etapa anterior. A sequência de convite é seguida por 200 OK e ACK, e o cliente de chat persistente agora abriu uma sessão SIP com um ponto de extremidade de servidor de chat persistente. Consequentemente, o cliente de chat persistente se comunica com o servidor de chat persistente enviando mensagens de informações de SIP que contenham mensagens de chat ou comandos solicitando que o servidor execute uma ação. Todas essas mensagens são reconhecidas com 200 OK ou 503 Serviço Não Disponível (isto é, no caso de uma grande carga no servidor). Se o cliente receber uma resposta 503, irá tentar novamente a mensagem. (Este exemplo não inclui uma resposta 503.) Se o servidor aceitar a mensagem ou comando e enviar 200 OK, ele fornecerá uma resposta para o cliente na forma de uma mensagem de informações SIP separada. Essa resposta inclui uma referência ao comando que a originou.

3.  O cliente de chat persistente envia uma mensagem de informações de SIP que contém o comando XCCOS **GetServerInfo** . Servidor de chat persistente responde com uma nova mensagem de informações de SIP que contém informações sobre a configuração do serviço de chat persistente.

4.  O cliente de chat persistente envia uma mensagem de informações de SIP que contém o comando XCCOS **getassociations** . O servidor de chat persistente responde com uma nova mensagem de informações de SIP que contém a lista de salas das quais o usuário é membro. O cliente de chat persistente repete o comando para recuperar a lista de salas das quais o usuário é um gerente.

5.  O cliente de chat persistente Obtém a lista de salas seguidas do documento "presença", onde cada sala seguida é representada por uma categoria "roomSetting". Todas as salas seguintes são reunidas por uma única mensagem SIP INFO que contém o comando XCCOS **bjoin**, que contém a lista de salas URIs. Por a lista de salas subsequentes ser mantida no servidor, qualquer cliente em qualquer computador possui a mesma lista de salas subsequentes para o usuário URI especificado. O cliente de chat persistente também mantém a lista de salas abertas (se essa opção estiver habilitada pelo usuário) no registro do computador local e ingressa em cada uma dessas salas ao entrar enviando uma mensagem SIP que contém o comando XCCOS **Join** para cada sala aberta. Como essa lista é mantida no registro, ela pode ser diferente em dois clientes de chat persistente executados em computadores diferentes.

6.  Para cada sala associada, o cliente de chat persistente envia uma mensagem de informações de SIP que contém o comando XCCOS **bccontext** . O servidor de chat persistente responde com uma nova mensagem de informações de SIP que contém a mensagem de chat mais recente na sala.

7.  O cliente de chat persistente envia uma mensagem de informações de SIP que contém um comando XCCOS **getinv** (ou seja, Get convite) para solicitar novos convites de sala que o cliente ainda não tenha visto. Em uma mensagem de informações SIP separada, o servidor de chat persistente retorna uma lista dessas salas.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>Inscrever-se para uma sala e postar uma mensagem

As etapas e o diagrama de fluxo de chamadas a seguir descrevem um cenário típico de assinatura de sala e postagem de mensagem.

**Fluxo de chamadas de assinatura e lançamento de mensagens de salas de cliente de chat persistente**

![Cenário de assinatura de sala e de postagem de mensagem.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Cenário de assinatura de sala e de postagem de mensagem.")

1.  No cliente de chat persistente, o Usuário1 clica em **ingressar em uma sala de chat**, clica em **Pesquisar**e, em seguida, insere alguns critérios de pesquisa. O cliente de chat persistente envia uma mensagem de informações de SIP que contém o comando XCCOS **chansrch** (sala de pesquisa), junto com os critérios de pesquisa. O servidor de chat persistente consulta o banco de dados back-end e responde uma nova mensagem de informações de SIP que contém uma lista de salas disponíveis que atendem aos critérios de pesquisa.

2.  O User1 seleciona a sala de bate-papo que deseja participar e, então, clica em **Seguir esta sala**. O cliente de chat persistente envia um servidor de chat persistente uma mensagem de SIP que contém o comando XCCOS **Join** e a ID de sala da sala de chat selecionada pelo usuário. O servidor de chat persistente responde com uma mensagem de informações SIP que contém os dados de provisionamento.

3.  O cliente de chat persistente envia um servidor de chat persistente uma mensagem de informações SIP que contém o comando XCCOS **bccontext** (contexto de backchat). O servidor de chat persistente recupera o histórico de chat e o retorna ao cliente de chat persistente em uma mensagem de informações SIP separada. Neste ponto, o usuário insere a sala de bate-papo e está pronto para participar.

4.  O User1 insere uma nova mensagem e clica em **Enviar**. O cliente de chat persistente envia a mensagem para a sala de chat em um comando SIP INFO XCCOS **grpchat** . O servidor de chat persistente armazena uma cópia dessa nova mensagem no banco de dados de back-end de chat persistente.

5.  Servidor de chat persistente envia uma cópia separada da mensagem SIP INFO XCCOS **grpchat** para Usuário2, que já entrou na sala de chat.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Fluxos de chamadas de conformidade de chat persistente

O servidor de chat persistente usa o enfileiramento de mensagens (também conhecido como MSMQ) e um banco de dados de conformidade adicional (mgccomp) para processar dados de conformidade. Como exemplo de como os eventos de conformidade são processados, a sequência de eventos a seguir descreve como um evento de postagem de mensagem é processado.

1.  Um usuário posta uma mensagem em uma sala.

2.  Servidor de chat persistente coloca informações referentes ao evento em uma fila de enfileiramento de mensagens particular.

3.  O servidor de conformidade de chat persistente lê esse evento a partir da fila e o coloca no banco de dados do mgccomp para processamento posterior.

4.  Periodicamente, o servidor de conformidade de chat persistente processa um conjunto de eventos no banco de dados e os envia para o adaptador de conformidade de chat persistente para processamento.

5.  Se o adaptador processar com êxito os dados, o servidor de conformidade de chat persistente excluirá os eventos do banco de dados do mgccomp.

</div>

</div>

<span> </span>

</div>

</div>

</div>

