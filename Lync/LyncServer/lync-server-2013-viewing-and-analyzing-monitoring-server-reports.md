---
title: 'Lync Server 2013: Exibindo e analisando relatórios do Monitoring Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9970e4c440148cac2002088212a48283c86184eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Exibindo e analisando relatórios do Monitoring Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-19_

Os relatórios do Monitoring Server oferecem várias medidas diferentes de qualidade de voz para monitorar a QoE que está sendo entregue aos usuários finais. Além disso, o monitoramento do servidor inclui vários relatórios internos que sua organização pode usar para observar as tendências de uso e qualidade de mídia na rede da sua organização e solucionar problemas de qualidade de mídia que surgem.

Uma parte principal de manter relatórios de servidor de monitoramento interessantes para operações diárias e semanais é exibir e analisar relatórios de qualidade de mídia, em particular:

  - Relatórios de resumo/tendências de QoE

  - Relatórios de desempenho de QoE

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Exibir relatórios do servidor de monitoramento

1.  Em um navegador da Web, localize os servidores que hospedam o SQL Reporting Services.

2.  Exibir os relatórios necessários na tela do navegador.

3.  Opcion Exporte um relatório selecionando a opção Exportar e o formato de saída necessário.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Configurar o registro de detalhes das chamadas (CDR)

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha permissões equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.

4.  Na página **Registro de Detalhes de Chamada**, clique no site apropriado na tabela, clique em **Editar** e em **Mostrar Detalhes**.

5.  Para ativar a limpeza, selecione **habilitar limpeza para servidores de monitoramento**.

6.  Em **manter gravações de detalhes de chamada por duração máxima (dias):** selecione o número máximo de dias que as gravações de detalhes de chamada devem ser mantidas.

7.  Em **Manter dados de relatório de erros por um período máximo de (dias):** selecione o número máximo de dias que os relatórios de erros devem ser retidos.

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="configure-qoe"></a>Configurar QoE

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte Delegate Setup Permissions.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.

3.  Na barra de navegação à esquerda, clique em **Monitoramento e Arquivamento** e clique em **Dados de Qualidade de Experiência**.

4.  Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.

5.  Para ativar a limpeza, selecione **habilitar limpeza para servidores de monitoramento**.

6.  Em **manter gravações de detalhes de chamada por duração máxima (dias):** selecione o número máximo de dias que os dados de QoE devem ser mantidos.

7.  Clique em Confirmar.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Alterar a política de arquivamento

1.  A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.

4.  Clique em **Global** na lista de políticas, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar política de arquivamento - Global**, faça o seguinte:

6.  Para habilitar ou desabilitar o arquivamento interno para a implantação, marque ou desmarque a caixa de seleção **arquivar comunicações internas** .

7.  Para habilitar ou desabilitar o arquivamento externo para a implantação, marque ou desmarque a caixa de seleção **arquivar comunicações externas** .

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Aplicar uma política de arquivamento a um usuário

1.  A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar usuário do Lync Server** em **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.

6.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Usando relatórios de monitoramento no Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Relatório de comparação de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

