---
title: 'Lync Server 2013: detalhes do agendamento de reuniões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Detalhes de agendamento de reuniões no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Depois de fazer uma verificação para assegurar que nenhuma outra reunião esteja agendada na hora solicitada, a equipe de suporte a grandes reuniões, que lida com a solicitação, agenda a reunião no pool de grandes reuniões. Use o suplemento de reunião online para o Lync que está instalado com o cliente do Lync Server 2013 para executar essa tarefa, usando as credenciais de um usuário habilitado para o Lync Server no pool de reunião longa dedicada.

Para assegurar a melhor experiência do usuário, é importante agendar a grande reunião com os níveis de acesso corretos e as configurações da reunião que são apropriadas para as necessidades do organizador da reunião. Recomendamos as seguintes configurações de agendamento definidas nas opções de reunião do Lync:

  - Use um novo espaço de reunião para cada grande reunião em vez de reutilizar o espaço dedicado da reunião.

  - Especifique os níveis de acesso à reunião conforme segue:
    
      - Se pelo menos um convidado for externo à organização, defina o tipo de acesso à reunião para **qualquer pessoa (sem restrições**). Isso habilita você a evitar o gerenciamento de um possível grande lobby quando a reunião estiver em andamento.
    
      - Se a reunião for somente interna, defina o tipo de acesso à reunião como **Para qualquer pessoa da minha organização**.
        
        <div>
        

        > [!NOTE]  
        > Evite definir o tipo de acesso à reunião como <STRONG>Pessoas que eu convidar da minha empresa</STRONG>, pois, quando essa configuração é usada, os organizadores devem adicionar todos os endereços de email em uma lista de convidados e você não poderá convidar um grupo de distribuição.<BR>Evite definir o tipo de acesso à reunião como <STRONG>Apenas eu, o organizador da reunião</STRONG>, pois essa configuração exige que todos os participantes da reunião, inclusive os apresentadores, sejam colocados no lobby durante a reunião. A pessoa responsável pela execução da grande reunião deverá monitorar a escalação do lobby e aceitar os novos usuários que estiverem no lobby.

        
        </div>

  - Permita que usuários que ligam de telefones entrem na reunião automaticamente marcando a configuração **Chamadores entram diretamente**.

  - Convide explicitamente os seguintes usuários:
    
      - Organizador e representante da reunião (solicitante)
    
      - A lista de apresentadores fornecida pelo solicitante da reunião
    
    <div>
    

    > [!NOTE]  
    > Se o tipo de acesso à reunião estiver definido como <STRONG>Pessoas que eu escolher</STRONG>, será preciso adicionar explicitamente cada participante da grande reunião como convidado da reunião.

    
    </div>

  - Gerencie explicitamente os apresentadores, em vez de definir a opção de apresentador como um dos valores promovidos automaticamente. Certifique-se de adicionar os seguintes usuários como apresentadores:
    
      - Organizador e representante da reunião (solicitante)
    
      - A lista de apresentadores fornecida pelo solicitantes da grande reunião
    
    <div>
    

    > [!NOTE]  
    > Ao gerenciar explicitamente os apresentadores, você pode controlar o número de apresentadores, para que você possa limitar apresentadores a um número pequeno o suficiente para que seja possível ter uma reunião grande em vigor. Se a maioria dos participantes da reunião tiver a função de participante, serão reduzidas as chances de alguém acidentalmente assumir o controle da apresentação, excluir a apresentação do PowerPoint, ativar/desativar o áudio dos apresentadores e outras interrupções na reunião.

    
    </div>

  - Marque a configuração **Desativar o áudio de todos os participantes** para assegurar que apenas os apresentadores possam transmitir áudio para a reunião.

  - Marque a configuração **Bloquear vídeo dos participantes** para assegurar que apenas os apresentadores possam transmitir vídeo para a reunião.

A figura a seguir mostra as configurações recomendadas para o suplemento de reunião online do Lync.

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

