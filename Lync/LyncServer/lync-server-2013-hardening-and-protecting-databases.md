---
title: 'Lync Server 2013: proteção e proteção de bancos de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0254c77bb276add6f55ccff623c1fc2bec590102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536908"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Proteção e proteção dos bancos de dados do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-05_

O Microsoft Lync Server 2013 também depende dos bancos de dados do SQL Server para armazenar as informações do usuário, o estado da conferência, dados de arquivamento e CDRs (registros de detalhes de chamada). Você pode maximizar a disponibilidade de dados do Lync Server 2013 em bancos de dados de back-end do Lync Server, Particionando os dados do aplicativo de forma a melhorar a tolerância a falhas e simplificar a solução de problemas. Para alcançar essas metas, siga estas diretrizes:

  - **Usando as práticas**     recomendadas de particionamento de servidor Separe seus arquivos de sistema operacional, aplicativos e programas de seus arquivos de dados.

  - **Armazenar arquivos de log de transações e arquivos**     de banco de dados Armazene esses arquivos separadamente para aumentar a tolerância a falhas e otimizar a recuperação e armazená-los em um disco ou volume criptografado.

  - **Usando o clustering**     de servidor Agrupa os servidores de back-end para otimizar a disponibilidade do sistema do Lync Server 2013.

  - **Garantir que todos os backups de dados sejam criptografados e devidamente tratados**     As mídias de backup perdidas, descartadas ou colocadas incorreta podem representar uma ameaça significativa à segurança de dados para implantações do Lync Server 2013

Em qualquer servidor do Lync Server 2013, exceto servidor Standard Edition, a instância do SQL Server Express (instância do RTCLOCAL) não é acessível remotamente, e nenhuma exceção de firewall local é criada, exceto para o SQL Server Express em um servidor Standard Edition. Em um servidor Standard Edition, o banco de dados back-end e o CMS (Repositório de Gerenciamento Central) são configurados para serem acessados remotamente. Para proteger os bancos de dados SQL Server, é possível fazer o seguinte:

  - Personalizar o firewall do SQL Server Express nos servidores Standard Edition, limitando o escopo dos servidores que podem acessar remotamente o banco de dados. Por padrão, qualquer endereço IP pode acessar remotamente o banco de dados.

  - Usar o SQL Server Configuration Manager para especificar os protocolos, os endereços IP e as portas para acesso remoto do SQL Server:
    
      - O Lync Server 2013 usa o protocolo TCP/IP. Ele suporta IP versão 4 (IPv4), mas não IP versão 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > O Lync Server 2013 pode funcionar em uma rede com uma pilha de IP Dual habilitada.

        
        </div>
    
      - O Lync Server 2013 oferece suporte a vários endereços IP (cartões de endereço de rede de hospedagem múltipla). É possível especificar que o SQL Server escute somente endereços IP específicos (endereço individual ou por sub-rede) e use somente protocolos específicos.
    
      - O Lync Server 2013 oferece suporte a portas estáticas e dinâmicas do SQL Server.

  - Executar o SQL Server em uma porta estática (não padrão) e não executar o SQL Server Browser (para que não informe a porta que está escutando ao cliente). Isso requer uma configuração personalizada em cada cliente do SQL Server, incluindo servidores front-end, servidor de monitoramento, servidor de arquivamento e consoles administrativos (executando o Shell de gerenciamento do Lync Server, o painel de controle do Lync Server ou o construtor de topologias) e todos os outros servidores que executam os bancos de dados do Lync Server).

<div>


> [!NOTE]  
> O acesso aos bancos de dados precisa ser limitado aos administradores de banco de dados confiáveis. Um administrador de banco de dados mal-intencionado pode inserir ou modificar dados nos bancos de dados para adquirir privilégios nos servidores do Lync Server 2013 ou obter informações confidenciais dos serviços, mesmo se o administrador do banco de dados não tiver sido concedido acesso direto ou controle dos servidores do Lync Server 2013.



</div>

Para obter detalhes sobre as configurações personalizadas e a proteção de bancos de dados do SQL Server, consulte o artigo de blog NextHop, "using Lync Server 2010 with a Custom SQL Server Network Configuration" em [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) .

<div>


> [!NOTE]  
> Você também pode otimizar a segurança de sistemas operacionais e servidores de aplicativos e pode usar a política de grupo para implementar bloqueios de segurança em sua implantação do Lync Server. Para obter detalhes, consulte <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">proteção e proteção de servidores e aplicativos para o Lync Server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

