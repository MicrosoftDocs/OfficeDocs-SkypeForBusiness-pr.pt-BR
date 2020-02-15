---
title: Usando o analisador de práticas recomendadas para examinar sua implantação em busca de possíveis problemas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afda261fc3e57750afaabbf349eb31631adea275
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Usando o analisador de práticas recomendadas para verificar a implantação do Lync Server 2013 em busca de possíveis problemas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

Para executar um exame do Analisador de Práticas Recomendadas, é necessário especificar o seguinte:

  - **Credenciais**   para executar uma verificação, você deve fazer logon em um computador no qual o Best Practices Analyzer está instalado usando uma conta que seja membro do grupo local de administradores. Além disso, é necessário fazer logon usando uma conta de usuário que tenha os direitos e permissões necessários para executar os exames apropriados, ou é necessário especificar credenciais que tenham os direitos e permissões de usuário apropriados ao executar o Analisador de Práticas Recomendadas. Para obter detalhes, consulte [Group Memberships and User Rights Requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Escopo da verificação**   para especificar o escopo da verificação, selecione as categorias e servidores que você deseja verificar. Você pode selecionar todas as categorias, uma ou mais categorias ou um ou mais servidores dentro de uma categoria específica no seu ambiente do Lync Server.

  - **Tipo de verificação**   atualmente, a verificação de verificação de integridade é o único tipo de verificação disponível (selecionada por padrão). A Verificação de Integridade pode gerar um relatório que inclui erros, avisos e outras informações para todos os servidores especificados no escopo.

  - **Velocidade da rede**   as opções de velocidade de rede incluem LAN rápida (100 Mbps ou mais), LAN (10 Mbps), Wan rápida (1,5 Mbps) ou WAN (64 Kbps). O tempo estimado para completar o exame tem base nessa configuração. Essa configuração também é usada para definir o período de tempo limite. Durante o exame, o Analisador de Práticas Recomendadas espera uma resposta de um servidor durante um tempo especificado. Se não receber uma resposta dentro do período de tempo limite especificado, ele vai para o próximo servidor no exame. Em redes mais lentas, esse período de tempo limite especificado é maior para acomodar latências de rede maiores. Recomendamos a seleção do link mais lento em sua topologia para esse parâmetro de modo que a ferramenta não ultrapasse o tempo limite muito rápido.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Para examinar sua implantação do Lync Server 2013

1.  Faça logon em um computador no qual o Analisador de Práticas Recomendadas está instalado usando uma conta membro do grupo local Administradores, e com outros direitos e permissões necessárias.

2.  Clique em **Iniciar**, aponte para **todos os programas**, clique em **Microsoft Lync Server 2013**e em **analisador de práticas recomendadas**.

3.  Na tela **Boas-vindas**, clique em **Selecionar opções para uma nova verificação**.

4.  Na página **Conectar ao Active Directory**, verifique o nome especificado em **Servidor Active Directory** e execute uma das seguintes opções:
    
      - Para executar um exame usando as credenciais usadas para fazer logon no computador, clique em **Conectar ao servidor do Active Directory**.
    
      - Para especificar credenciais diferentes que você deseja usar para os Serviços de Domínio do Active Directory, Servidor de Borda ou Exchange Server, clique em **Mostrar opções avançadas de logon**, marca cada caixa de seleção para a qual as credenciais separadas são necessárias, especifique as credenciais para cada caixa de seleção marcada e clique em **Conectar ao servidor do Active Directory**.
    
    <div>
    

    > [!NOTE]
    > Antes de começar o exame, o Analisador de Práticas Recomendadas executa uma verificação de rede e de permissões a fim de assegurar que as credenciais de conta especificadas sejam válidas e que o Analisador de Práticas Recomendadas possa se conectar aos Serviços de Domínio do Active Directory. Se a ferramenta estiver em execução em um servidor de grupo de trabalho, a ferramenta também verificará se pode se conectar aos Servidores de Borda na rede de perímetro (ou seja, se estiverem incluídos no exame).

    
    </div>

5.  Na página **Iniciar uma nova verificação das Práticas Recomendadas**, selecione as opções que você deseja incluir no exame, especifique a velocidade da rede e clique em **Iniciar exame**.

6.  Na página **Verificação concluída**, clique em **Exibir um relatório desta verificação das Práticas Recomendadas**.

7.  Na página **Exibir Relatório das Práticas Recomendadas**, execute uma das seguintes ações:
    
      - Para exibir relatórios em uma lista organizada por componente do servidor, clique em **Listar Relatórios** e, em seguida, clique na guia **Todos os Problemas** ou na guia **Itens Informativos**.
    
      - Para exibir relatórios como uma lista hierárquica organizada por tipo de resultado, clique em **Relatórios em Árvore** e, em seguida, clique na guia **Exibição Detalhada** ou na guia **Exibição Resumida**.
    
      - Para exibir outros relatórios, clique em **Outros Relatórios**.
    
    <div>
    

    > [!NOTE]
    > Para obter detalhes sobre os relatórios do analisador de práticas recomendadas e os problemas que eles identificam, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">exibindo e trabalhando com relatórios criados pelo Best Practices Analyzer no Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisando e resolvendo problemas identificados pelo Best Practices Analyzer no Lync Server 2013</A>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

