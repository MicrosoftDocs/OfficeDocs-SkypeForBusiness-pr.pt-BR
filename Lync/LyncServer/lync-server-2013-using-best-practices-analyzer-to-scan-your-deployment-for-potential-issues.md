---
title: Usar o analisador de práticas recomendadas para verificar a implantação em busca de possíveis problemas
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
ms.openlocfilehash: 1f787268301570d4440240289c19fdd1e266a607
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Usar o analisador de práticas recomendadas para verificar a implantação do Lync Server 2013 em busca de possíveis problemas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-21_

Para executar uma verificação do analisador de práticas recomendadas, você deve especificar o seguinte:

  - **Credenciais**   para executar uma verificação, você deve fazer logon em um computador no qual o Best Practices Analyzer está instalado usando uma conta que seja membro do grupo Administradores local. Além disso, você precisa fazer logon usando uma conta de usuário que tenha os direitos de usuário e as permissões necessárias para executar as verificações adequadas ou especificar as credenciais que têm direitos e permissões de usuário apropriados ao executar o analisador de práticas recomendadas. Para obter detalhes, consulte [associações de grupo e requisitos de direitos de usuário para o analisador de práticas recomendadas no Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Escopo da verificação**   para especificar o escopo da verificação, selecione as categorias e os servidores que você deseja verificar. Você pode selecionar todas as categorias, uma ou mais categorias ou um ou mais servidores em uma categoria específica em seu ambiente do Lync Server.

  - **Tipo de verificação**   atualmente, a verificação de verificação de integridade é o único tipo de verificação disponível (selecionada por padrão). A verificação de verificação de integridade gera um relatório que inclui erros, avisos e outras informações para todos os servidores especificados no escopo.

  - ****   Opções de velocidade de rede de velocidade de rede incluem LAN rápida (100 Mbps ou mais), LAN (10 Mbps), rede remota rápida (1,5 Mbps) ou WAN (64 Kbps). O tempo estimado para concluir a verificação é baseado nessa configuração. Essa configuração também é usada para definir o período de tempo limite. Durante a verificação, o analisador de práticas recomendadas aguarda uma resposta de um servidor por um período especificado. Se não receber uma resposta dentro do período de tempo limite especificado, ela será movida para o próximo servidor na verificação. Em redes mais lentas, esse período de tempo limite especificado está mais em conta com latências de rede mais longas. Recomendamos que você selecione o link mais lento na sua topologia para esse parâmetro, para que a ferramenta não tenha tempo limite muito rápido.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Para verificar a implantação do Lync Server 2013

1.  Faça logon em um computador no qual o analisador de práticas recomendadas está instalado usando uma conta que é membro do grupo Administradores local e tem outros direitos e permissões de usuário necessários.

2.  Clique em **Iniciar**, aponte para **todos os programas**, clique em **Microsoft Lync Server 2013**e, em seguida, clique em **analisador de práticas recomendadas**.

3.  Na tela de **boas-vindas** , clique em **selecionar opções para uma nova digitalização**.

4.  Na página **conectar-se ao Active Directory** , verifique o nome especificado no **servidor do Active Directory**e siga um destes procedimentos:
    
      - Para executar uma verificação usando as credenciais que você usou para fazer logon no computador, clique em **conectar-se ao servidor do Active Directory**.
    
      - Para especificar credenciais diferentes que você deseja usar nos serviços de domínio Active Directory, no servidor de borda ou no Exchange Server, clique em **Mostrar opções de logon avançadas**, marque cada caixa de seleção para a qual as credenciais separadas são necessárias, especifique as credenciais para cada caixa de seleção e clique em **conectar ao servidor do Active Directory**.
    
    <div>
    

    > [!NOTE]
    > Antes de iniciar a verificação, o analisador de práticas recomendadas executa uma verificação de rede e permissões para garantir que as credenciais de conta especificadas sejam válidas e que o analisador de práticas recomendadas possa se conectar aos serviços de domínio do Active Directory. Se a ferramenta estiver em execução em um servidor de grupo de trabalho, a ferramenta também verificará se ela pode se conectar a servidores de borda na rede de perímetro (isto é, se estiverem incluídos na verificação).

    
    </div>

5.  Na página **iniciar uma nova verificação de práticas recomendadas** , selecione as opções que você deseja incluir na verificação, especifique a velocidade da rede e clique em **Iniciar verificação**.

6.  Na página **scanning Completed Completed** , clique em **exibir um relatório desta análise de práticas recomendadas**.

7.  Na página **Exibir relatório de práticas recomendadas** , siga um destes procedimentos:
    
      - Para exibir relatórios em uma lista organizada por componente de servidor, clique em **relatórios de lista**e, em seguida, clique na guia **todos os problemas** ou **itens informativos** .
    
      - Para exibir relatórios como uma lista hierárquica organizada por tipos de resultados, clique em **relatórios de árvore**e, em seguida, clique na guia modo de **exibição detalhado** ou na guia **modo de exibição de resumo** .
    
      - Para ver outros relatórios, clique em **outros relatórios**.
    
    <div>
    

    > [!NOTE]
    > Para obter detalhes sobre os relatórios do analisador de práticas recomendadas e os problemas que eles identificam, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">exibindo e trabalhando com relatórios criados pelo analisador de práticas recomendadas no Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisando e resolvendo problemas identificados pelo analisador de práticas recomendadas no Lync Server 2013</A>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

