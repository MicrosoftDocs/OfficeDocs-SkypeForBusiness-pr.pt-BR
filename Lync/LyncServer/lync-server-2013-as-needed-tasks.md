---
title: 'Lync Server 2013: tarefas necessárias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98b4323374c9801ec07930941a0daa3635b04e43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529538"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a>Tarefas necessárias no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-18_

Execute as seguintes tarefas, conforme necessário. Eles também são freqüentemente cobertos por procedimentos padrão:

  - **Auditoria de segurança completa   ** Você pode executar essa auditoria regularmente, em resposta a uma atualização ou reformulação do sistema de mensagens, ou em resposta a uma falha de segurança tentada (ou bem-sucedida). O procedimento pode envolver verificações de porta em servidores e firewalls, auditorias de correções de segurança e testes de penetração de terceiros.

  - **Substituir certificados prestes a expirar**     A verificação de certificados do Lync Server é uma das tarefas periódicas regulares e, como parte do procedimento, um administrador deve ter um registro de todas as datas de vencimento dos certificados. Este registro permite que um administrador crie uma notificação quando um determinado certificado estiver prestes a expirar e substituído conforme necessário.

  - **Atualizando linhas de base**     de desempenho Atualize as linhas de base de desempenho após uma atualização ou alteração de configuração. Sua organização pode usar linhas de base para medir as alterações de desempenho e detectar problemas que afetam o desempenho do sistema.

  - **Gerenciando o pool corporativo**     A configuração inicial dos pools corporativos, dos servidores Standard Edition e de qualquer outro servidor no ambiente da organização foi feita durante a implantação dos servidores individuais. O gerenciamento pós-implantação de servidores e pools para servidores Standard Edition e pools corporativos inclui as seguintes tarefas:
    
      - Gerenciando servidores front-end
    
      - Gerenciando Webconferência
    
      - Gerenciando conferência
    
      - Alterar credenciais da conta de serviço
    
      - Gerenciando bancos de dados
    
      - Iniciar e interromper serviços e desativação de funções de servidor
    
      - Remover servidores e funções de servidor, remover pools e encerrar servidores e pools

  - **Gerenciando o uso**     Você pode configurar o Lync Server 2013 para fornecer os recursos e a funcionalidade mais adequados para sua organização. Isso inclui:
    
      - Gerenciando o suporte para reuniões da webconferência no local
    
      - Gerenciando o uso de grupos de distribuição para enviar mensagens instantâneas
    
      - Gerenciando contatos, presença e consultas
    
      - Configurando a filtragem de versão do cliente
    
      - Configurando a filtragem inteligente de IM
    
      - Configurando arquivamento, registro de detalhes das chamadas e conformidade da reunião

  - **Gerenciando a conectividade**     do servidor de borda O gerenciamento contínuo dos servidores e das configurações necessárias para fornecer conectividade externa inclui o seguinte:
    
      - Gerenciando a conectividade entre servidores internos e servidores de borda
    
      - Configurando interfaces e certificados internos e externos para servidores de borda
    
      - Gerenciando o acesso de parceiro federado

  - **Administrar o catálogo**     de endereços Administrar servidores de catálogo de endereços inclui o seguinte:
    
      - Configurando a normalização de telefone do servidor do catálogo de endereços
    
      - Gerenciando o servidor de catálogo de endereços a partir da linha de comando

  - **Gerenciando contas**     de usuário O gerenciamento de contas de usuário inclui o seguinte:
    
      - Habilitar contas de usuário para o Lync Server
    
      - Configurando usuários do Lync Server usando o assistente
    
      - Configurando propriedades individuais de contas de usuário do Lync Server
    
      - Pesquisando usuários do Lync Server
    
      - Movendo usuários do Lync Server
    
      - Excluir usuários do Lync Server

  - **Analisando arquivos**     de log do Lync Server 2013 Uma ferramenta muito útil, geralmente usada para solução de problemas, é a ferramenta de registro em log do Lync Server 2013 descrita em detalhes em [using Lync server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).

Como a ferramenta de registro em log gera arquivos de log (em uma base por servidor), esses arquivos de log podem ser visualizados e analisados usando a ferramenta Snooper, se as ferramentas do Microsoft Office Server 12 Resource Kit estiverem instaladas no computador. Caso contrário, os logs também podem ser analisados usando um editor de texto, que é muito menos transparente e mais complexo do que o uso do utilitário Snooper.

Para exibir e analisar mensagens de protocolo

Na ferramenta de log, depois de finalizar a sessão de depuração, clique em analisar arquivos de log para exibir os arquivos de log usando a ferramenta Snooper. Você pode analisar os logs de protocolo para os seguintes componentes:

  - Lync Server SipStack (SIP)

  - S4 (SIP) do Lync Server

  - C3P (tráfego de sinalização de conferência do Lync Server), incluindo MCU-C3P e foco C3P

  - Tráfego de Webconferência do Lync Server (PSOM)

  - Cliente de plataforma de comunicação unificada do Lync Server (UCCP)

  - Relatórios de erro do banco de dados de arquivamento

Para ajudar a organizar o desempenho das tarefas necessárias, confira As-Needed lista de verificação de operações.

<div>


> [!IMPORTANT]  
> Para obter procedimentos detalhados de administração e gerenciamento, consulte o guia de administração do Microsoft Lync Server 2013.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Políticas de backup (e restauração) ou definições de configuração

O Lync Server 2013 permite fazer backup e restaurar todo o sistema. IIf que você deseja fazer backup (e, em seguida, pode ser uma restauração de algum dia) uma única política ou uma única coleção de definições de configuração, recuperar a política apropriada e, em seguida, canalizar esse objeto para o cmdlet Export-Clixml, que salva as informações de política como um arquivo XML:

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

Agora você pode experimentar o RedmondClientPolicy e alterar muitas das configurações. Se decidir em vez de restaurar a política antiga, digite:

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Observe que essa abordagem funcionará para a maioria das políticas e configurações, mas não funcionará com alguns dos itens mais complexos, os itens que contêm vários subobjetos (como configurações de roteamento, que contêm muitas rotas de voz separadas).

</div>

</div>

<span> </span>

</div>

</div>

</div>

