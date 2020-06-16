---
title: Processo de migração-detalhes
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76624475b86427d8e3b1aa4f9efa75c127afcb85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>Processo de migração-detalhes

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Use os seguintes pré-requisitos e etapas detalhadas para migrar o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat para o Lync Server 2013, servidor de chat persistente.

<div>

## <a name="prerequisites-for-migration"></a>Pré-requisitos para migração

Certifique-se de que você tenha atendido aos seguintes pré-requisitos antes de migrar o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat para o Lync Server 2013, servidor de chat persistente.

1.  Implante pelo menos um pool do Lync Server 2013. Se você tiver vários pools do Lync Server 2013, decida qual pool do Lync Server 2013 será o pool de Home para o novo pool do servidor de chat persistente do Lync Server 2013.

2.  Instale o pool do servidor de chat persistente do Lync Server 2013. Ele estará vazio (sem categorias, salas ou suplementos). Antes de migrar suas categorias, salas ou suplementos herdados, você pode criar salas, categorias ou suplementos em sua implantação do Lync Server 2013, persistent chat Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Lembre-se de que esses itens recém-criados podem entrar em conflito com itens herdados migrados. Evitar qualquer conflito de nomes; caso contrário, eles serão substituídos quando os dados herdados forem migrados.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Preparando os dados de origem para migração

Execute as seguintes etapas para preparar adequadamente os dados de origem para a migração.

1.  Faça backup dos bancos de dados de origem para o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat. Para obter detalhes sobre como fazer backup do SQL Server, consulte "visão geral do backup (SQL Server)" em <https://go.microsoft.com/fwlink/p/?linkid=254851> .
    
    <div>
    

    > [!IMPORTANT]  
    > Os serviços de domínio do Active Directory devem ser os mesmos. Como uma condição para migração, você não pode migrar para um pool em uma implantação diferente (especificamente, em uma floresta diferente do Active Directory).

    
    </div>

2.  Inspecione seu Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat Chat e configuração de categoria. Quaisquer alterações em categorias, salas ou suplementos em sua implantação herdada existente serão feitas pela ferramenta de administração de chat de grupo.
    
    <div>
    

    > [!TIP]  
    > Quaisquer alterações em categorias, salas ou suplementos no Lync Server 2013, implantação de servidor de chat persistente são realizadas pelo painel de controle do Lync Server ou cmdlets do Windows PowerShell.

    
    </div>
    
    Siga estas etapas para preparar seu sistema herdado para migração.
    
    1.  O servidor de chat persistente oferece suporte a um único nível de categorias, ao contrário de um conjunto hierárquico profundo de categorias. Após a migração, as subcategorias são prefixadas com nomes de categoria pai completo. Convém simplificar e achatar sua estrutura de categorias existente para que a estrutura resultante atenda às suas necessidades.
    
    2.  Verifique os **gerentes** na categoria raiz. Se existirem gerentes nesse nível, esses usuários serão adicionados como **gerentes a todas as salas** após a migração. Se isso não for um requisito para sua organização, você precisa remover esses gerentes da categoria raiz.
    
    3.  Verifique o tamanho dos nomes de sala. Após a migração, devido às estruturas de categoria simplificadas, se as salas existirem em uma categoria filha, elas serão prefixadas com nomes de categoria pai completo. O limite de nomenclatura é de 256 caracteres, incluindo nomes de categoria pai. Você deve verificar o tamanho dos nomes de sala e possivelmente diminuir o comprimento, se eles forem muito longos.
    
    4.  No Lync Server 2013, se as configurações de **convites** de categoria estiverem definidas como true, você poderá escolher true ou false para convites para salas nessa categoria. No entanto, se as configurações de convites de categoria estiverem definidas como false, as salas nessa categoria têm convites desativados. Antes da migração, você deve redefinir as configurações de convite em sua versão do servidor de chat de grupo do Lync Server herdado, se quiser que a (s) sala (s) exista em uma categoria específica. Caso contrário, durante a migração, o Lync Server 2013 exibe avisos e define salas como o valor padrão de false.
    
    5.  Se você usou arquivos em salas de chat, deve usar o XCOPY manualmente os arquivos para o novo repositório de arquivos de chat persistente após a migração. As ferramentas não fazem isso.
    
    6.  Se você tivesse usuários federados e salas com usuários federados, lembre-se de que o servidor de chat persistente não dá suporte à Federação. As salas com usuários federados serão migradas; no entanto, os usuários propriamente ditos não poderão acessar o conteúdo, pois o acesso federado não é suportado.
    
    7.  Identifique as salas que você não deseja migrar e marque-as como desabilitadas.
    
    8.  Identifique a data além da qual você deseja migrar o conteúdo da sala de chat. Por exemplo, talvez você não queira migrar mensagens antes de 1º de janeiro de 2010, pois essas mensagens podem ser obsoletas ou não relevantes para a migração.

</div>

<div>

## <a name="performing-the-migration"></a>Realizando a migração

Execute as seguintes etapas para migrar seu servidor de chat de grupo herdado.

1.  Desligue o Lync Server 2010, o chat de grupo, o Office Communications Server 2007 R2 Group Chat ou o Lync Server 2013, serviços do servidor de chat persistente. Todos os serviços devem ser interrompidos, portanto, planeje isso de cada vez, quando houver tempo de inatividade suficiente. Conforme descrito anteriormente, certifique-se de fazer backup do banco de dados de chat de grupo atual.

2.  Execute o cmdlet **Export-CsPersistentChatData** do Windows PowerShell como membro da função RBAC do administrador de chat persistente (CsPersistentChatAdministrator). Para obter detalhes sobre os cmdlets Export/Import, consulte [Solucionando problemas de configuração do servidor de chat persistente usando cmdlets do Windows PowerShell no Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Inspecione o conteúdo exportado.

3.  Antes de estar pronto para importar, desative o Lync Server 2013, serviços do servidor de chat persistente. Todos os serviços precisam ser interrompidos, portanto, planeje isso por vez, quando houver tempo de inatividade suficiente.

4.  Execute um backup do banco de dados de chat persistente se você tiver criado quaisquer categorias, salas ou suplementos na sua implantação do Lync Server 2013 antes da migração. O processo de exportação/importação será capaz de mesclar os dados herdados na implantação do Lync Server 2013, mas você desejará fazer o backup do banco de dados caso o conteúdo seja substituído inadvertidamente (por exemplo, se ainda existirem conflitos de nomenclatura).

5.  Execute o cmdlet **Import-CsPersistentChatData** do Windows PowerShell (ferramenta de importação), com um comando **WhatIf** para preencher o servidor back-end do pool do servidor de chat persistente com os dados migrados. Algumas conversões acontecem no processo para acomodar o modelo de administração simplificado. Correção de erros ou avisos exibidos.

6.  Execute o servidor de chat persistente do Windows PowerShell **Import-CsPersistentChatData** cmdlet como um membro da função RBAC do administrador de chat persistente (CsPersistentChatAdministrator). Para obter detalhes sobre os cmdlets Export/Import, consulte [Solucionando problemas de configuração do servidor de chat persistente usando cmdlets do Windows PowerShell no Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Você deve XCOPY todos os arquivos carregados (a pasta inteira) para o novo repositório de arquivos de chat persistente do Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > O Lync 2013 (cliente) não suporta carregar ou exibir arquivos em salas de chat. Você ainda pode usar o cliente herdado para postar e exibir arquivos na sala.

    
    </div>

8.  Port o Lync Server 2010, o chat de grupo ou o URI do servidor de pesquisa de chat do grupo do Office Communications Server 2007 R2 para o Lync Server 2013, o objeto de contato do servidor de chat persistente. As etapas a seguir são necessárias se seus clientes de chat de grupo do Lync 2010 ou do Office Communicator 2007 R2 precisarem se conectar ao Lync 2013, persistente chat (cliente) mais recente após a migração sem qualquer alteração de configuração do lado do cliente:
    
      - Exclua a \<domainName\> conta de usuário do servidor de pesquisa do OCSChat@. com. Isso foi usado para apontar para o serviço de pesquisa no Lync Server 2010, chat de grupo. Você pode desinstalar o pool e remover as entradas confiáveis mais tarde.
    
      - Crie um ponto de extremidade herdado (objeto de contato do servidor de chat persistente) executando o cmdlet do Windows PowerShell, **New-CsPersistentChatEndpoint**, com o URI SIP idêntico para que o cliente herdado funcione efetivamente quando o serviço for reiniciado.
    
    O processo de migração obrigatório está completo neste ponto. Lync 2010 Group Chat (clientes) ou Office Communicator 2007 R2 Group Chat (clientes) podem se conectar ao novo pool de servidor de chat persistente agora, de forma transparente.
    
    Siga estas etapas adicionais de descomissionamento para o Lync Server 2010, o chat de grupo ou o Office Communications Server 2007 R2 Group Chat.

9.  Inicie os serviços do servidor de chat persistente, ativando todos os computadores no novo pool do servidor de chat persistente.

10. Use o painel de controle do Lync Server e os cmdlets do Windows PowerShell para verificar se os dados foram migrados com êxito.

11. Desinstalar o Lync 2010 Group Chat ou o chat de grupo do Office Communicator 2007 R2 dos computadores no pool do servidor de chat de grupo.

12. Exclua o aplicativo confiável e o pool de aplicativos confiáveis usando os cmdlets do Windows PowerShell. Isso exclui esses itens do repositório de gerenciamento central e das entradas de serviço confiáveis (TSEs) associadas do Active Directory. Como alternativa, essa etapa funciona usando o construtor de topologias (os aplicativos/pools confiáveis têm um nó dedicado, também).

13. Agora você pode começar a habilitar a funcionalidade do servidor de chat persistente através dos novos clientes. Para obter detalhes sobre como habilitar o servidor de chat persistente, consulte [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > O Lync Server 2013 oferece suporte a vários pools de servidores de chat persistente. No entanto, damos suporte à migração de um chat de grupo do Lync 2010 ou do pool de chat de grupo do Office Communications Server 2007 R2 &nbsp; para um único servidor Lync server 2013, persistente pool do servidor de chat. Você pode adicionar novos pools de servidores de chat persistentes à sua implantação para atender às necessidades normativas (por exemplo, manter dados dentro de uma determinada Geografia).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

