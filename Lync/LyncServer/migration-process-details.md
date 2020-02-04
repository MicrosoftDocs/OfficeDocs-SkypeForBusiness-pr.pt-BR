---
title: Processo de migração - detalhes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d3b46e2b80d9ad5a4b08108d1dc2bad03cf5f0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>Processo de migração - detalhes

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Use os seguintes pré-requisitos e etapas detalhadas para migrar o Lync Server 2010, o chat em grupo ou o Office Communications Server 2007 R2 Grupo chat para o Lync Server 2013, servidor de chat persistente.

<div>

## <a name="prerequisites-for-migration"></a>Pré-requisitos para migração

Certifique-se de que você tenha atendido aos seguintes pré-requisitos antes de migrar o Lync Server 2010, o chat em grupo ou o Office Communications Server 2007 R2 Grupo chat para o Lync Server 2013, servidor de chat persistente.

1.  Implante pelo menos um pool do Lync Server 2013. Se você tiver vários pools do Lync Server 2013, decida qual o pool do Lync Server 2013 será o pool primário do novo pool de servidores de chat persistente do Lync Server 2013.

2.  Instale o pool do servidor de chat persistente do Lync Server 2013. Ele estará vazio (não há nenhuma categoria, sala ou suplementos). Antes de migrar suas categorias, salas ou suplementos herdados, você pode criar salas, categorias ou suplementos no Lync Server 2013, implantação persistente do servidor de chat.
    
    <div>
    

    > [!IMPORTANT]  
    > Lembre-se de que esses itens recém-criados podem entrar em conflito com itens herdados que você migrar. Evitar conflitos de nomes; caso contrário, eles serão substituídos quando os dados herdados forem migrados.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Preparando os dados de origem para a migração

Execute as etapas a seguir para preparar adequadamente os dados de origem para a migração.

1.  Faça backup dos bancos de dados de origem para o Lync Server 2010, o chat em grupo ou o Office Communications Server 2007 R2 Grupo chat. Para obter detalhes sobre o backup do SQL Server, consulte "visão geral de backup (SQL Server <http://go.microsoft.com/fwlink/p/?linkid=254851>)" em.
    
    <div>
    

    > [!IMPORTANT]  
    > Os serviços de domínio Active Directory devem ser iguais. Como uma condição para a migração, não é possível migrar para um pool em uma implantação diferente (especificamente, em uma floresta do Active Directory diferente).

    
    </div>

2.  Inspecione o Lync Server 2010, o chat em grupo ou o Office Communications Server 2007 R2 grupo salas de chat e configuração de categoria. Todas as alterações em categorias, salas ou suplementos em sua implantação herdada existente serão feitas pela ferramenta de administração de chat em grupo.
    
    <div>
    

    > [!TIP]  
    > Todas as alterações em categorias, salas ou suplementos no Lync Server 2013, a implantação persistente do servidor de chat são realizadas pelo painel de controle do Lync Server ou cmdlets do Windows PowerShell.

    
    </div>
    
    Siga estas etapas para preparar seu sistema herdado para migração.
    
    1.  O servidor de chat persistente dá suporte a um único nível de categorias, ao contrário de um conjunto hierárquico profundo de categorias. Após a migração, as subcategorias são prefixadas com nomes de categoria pai completo. Convém simplificar e achatar a estrutura de categorias existente para que a estrutura resultante atenda às suas necessidades.
    
    2.  Verifique os **gerentes** na categoria raiz. Se houver gerentes nesse nível, esses usuários serão adicionados como **gerentes a todas as salas** após a migração. Se isso não for um requisito para sua organização, você precisará remover esses gerentes da categoria raiz.
    
    3.  Verifique a duração dos nomes de sala. Após a migração, devido a estruturas de categoria simplificadas, se as salas existirem em uma categoria filho, elas serão prefixadas com nomes de categoria pai completo. O limite de nomenclatura é de 256 caracteres, incluindo nomes de categoria pai. Você deve verificar a extensão dos nomes da sala e possivelmente diminuir o comprimento, se eles forem muito longos.
    
    4.  No Lync Server 2013, se as configurações de **convites** de categoria estiverem definidas como verdadeiro, você poderá escolher verdadeiro ou falso para convites para salas sob essa categoria. No entanto, se as configurações de convites de categoria estiverem definidas como falso, as salas sob essa categoria têm convites desativados. Antes da migração, você deve redefinir as configurações de convite em sua versão do servidor de chat de grupo herdado do Lync Server, se quiser que as salas estejam em uma categoria específica. Caso contrário, durante a migração, o Lync Server 2013 exibe avisos e define salas para o valor padrão de false.
    
    5.  Se você usou arquivos em salas de chat, deve XCOPY os arquivos manualmente para o novo repositório de arquivos de chat persistente após a migração. As ferramentas não fazem isso.
    
    6.  Se você tiver usuários federados e salas com usuários federados, lembre-se de que o servidor de chat persistente não oferece suporte à Federação. Salas com usuários federados serão migrados; no entanto, os usuários propriamente ditos não poderão acessar o conteúdo, porque o acesso federado não é compatível.
    
    7.  Identifique as salas que você não deseja migrar e marque-as como desabilitadas.
    
    8.  Identifique a data além da qual você deseja migrar o conteúdo da sala de chat. Por exemplo, talvez você não queira migrar as mensagens antes de 1º de janeiro de 2010, pois essas mensagens podem ficar obsoletas ou não relevantes para a migração.

</div>

<div>

## <a name="performing-the-migration"></a>Executar a migração

Execute as seguintes etapas para migrar seu servidor de chat de grupo herdado.

1.  Desligar o Lync Server 2010, o chat em grupo, o Office Communications Server 2007 R2 Grupo chat ou o Lync Server 2013, serviços persistentes do servidor de chat. Todos os serviços devem ser interrompidos, portanto, planeje isso quando houver tempo ocioso suficiente. Conforme descrito anteriormente, certifique-se de fazer backup do banco de dados de chat em grupo atual.

2.  Execute o cmdlet **Export-CsPersistentChatData** do Windows PowerShell como membro da função RBAC do administrador de chat persistente (CsPersistentChatAdministrator). Para obter detalhes sobre os cmdlets de exportação/importação, consulte [solução de problemas de configuração do servidor de chat persistente usando cmdlets do Windows PowerShell no Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Inspecione o conteúdo exportado.

3.  Antes de estar pronto para importar, desligue o Lync Server 2013, serviços persistentes do servidor de chat. Todos os serviços precisam ser interrompidos, portanto, planeje isso quando houver tempo ocioso suficiente.

4.  Execute um backup do banco de dados de chat persistente se você tiver criado qualquer categoria, sala ou suplemento em sua implantação do Lync Server 2013 antes da migração. O processo de exportação/importação poderá mesclar os dados herdados na implantação do Lync Server 2013, mas você desejará fazer backup do banco de dados caso o conteúdo seja substituído inadvertidamente (por exemplo, se ainda houver conflitos de nomes).

5.  Execute o cmdlet **Import-CsPersistentChatData** do Windows PowerShell (ferramenta de importação), com um comando **WhatIf** para popular o servidor back-end do pool do servidor de chat persistente com dados migrados. Algumas conversões acontecem no processo para acomodar o modelo de administração simplificado. Corrija todos os erros ou avisos exibidos.

6.  Execute o cmdlet do Windows PowerShell **Import-CsPersistentChatData** do servidor de chat persistente como membro da função RBAC do administrador de chat persistente (CsPersistentChatAdministrator). Para obter detalhes sobre os cmdlets de exportação/importação, consulte [solução de problemas de configuração do servidor de chat persistente usando cmdlets do Windows PowerShell no Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Você deve XCOPY todos os arquivos carregados (a pasta inteira) para o novo Lync Server 2013, o armazenamento de arquivos de chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > O Lync 2013 (cliente) não tem suporte para carregar ou exibir arquivos em salas de chat. Você ainda pode usar o cliente herdado para postar e exibir arquivos na sala.

    
    </div>

8.  Porta do Lync Server 2010, chat em grupo ou URI do servidor de pesquisa de chat de grupo do Office Server 2007 R2 para o Lync Server 2013, objeto de contato persistente do servidor de chat. As etapas a seguir são necessárias se os clientes de chat de grupo do Lync 2010 ou do Office Communicator 2007 R2 precisarem se conectar ao Lync 2013, o chat persistente (cliente) mais recente após a migração sem nenhuma alteração de configuração do lado do cliente:
    
      - Exclua o\<OCSChat@ conta de\>usuário do servidor de pesquisa DomainName. com. Isso foi usado para apontar para o serviço de pesquisa no Lync Server 2010, chat em grupo. Você pode desinstalar o pool e remover as entradas confiáveis mais tarde.
    
      - Crie um ponto de extremidade herdado (objeto de contato do servidor de chat persistente) executando o cmdlet do Windows PowerShell, **New-CsPersistentChatEndpoint**, com o URI SIP idêntico para que o cliente herdado funcione efetivamente quando o serviço for reiniciado.
    
    O processo de migração obrigatório está completo neste ponto. O Lync do Lync 2010 (clientes) ou o chat de grupo do Office Communicator 2007 R2 (clientes) podem se conectar ao novo pool de servidores de chat persistente agora, de forma transparente.
    
    Siga estas etapas adicionais de descomissionamento para o Lync Server 2010, o chat em grupo ou o Office Communications Server 2007 R2 Grupo chat.

9.  Inicie os serviços persistentes do servidor de chat ativando todos os computadores no novo pool de servidores de chat persistente.

10. Use o painel de controle do Lync Server e cmdlets do Windows PowerShell para verificar se os dados foram migrados com êxito.

11. Desinstale o chat em grupo do Lync 2010 ou o chat de grupo do Office Communicator 2007 R2 dos computadores no pool do servidor de chat do grupo.

12. Exclua o aplicativo confiável e o pool de aplicativos confiável usando cmdlets do Windows PowerShell. Isso exclui esses itens do repositório de gerenciamento central e as entradas de serviço confiáveis associadas (TSEs) do Active Directory. Como alternativa, essa etapa funciona usando o construtor de topologias (os aplicativos/pools confiáveis têm um nó dedicado, também).

13. Agora você pode começar a habilitar a funcionalidade do servidor de chat persistente por meio dos novos clientes. Para obter detalhes sobre como habilitar o servidor de chat persistente, consulte [implantando o servidor de chat persistente no Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > O Lync Server 2013 dá suporte a vários pools de servidores de chat persistentes. No entanto, damos suporte à migração de um chat em grupo do Lync 2010&nbsp;ou do pool de chat do grupo do Office Communications Server 2007 R2 para um único Lync Server 2013, pool persistente do servidor de chat. Você pode adicionar mais novos pools de servidores de chat persistentes à sua implantação para atender às necessidades normativas (por exemplo, manter dados dentro de uma determinada Geografia).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

