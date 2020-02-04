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
ms.openlocfilehash: 9e4fce6cf17601d2a68a07a3b832e6b50c10b759
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Visualizando e analisando relatórios do Monitoring Server no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-19_

Os relatórios do Monitoring Server fornecem várias medidas diferentes de qualidade de voz para monitorar a QoE que está sendo entregue aos usuários finais. Além disso, o Monitoring Server inclui vários relatórios internos que a sua organização pode usar para monitorar o uso e as tendências de qualidade de mídia na rede da sua organização e solucionar problemas de qualidade de mídia que surgem.

Uma parte principal de manter os relatórios do servidor de monitoramento interessantes para operações semanais e semanais é exibir e analisar relatórios de qualidade de mídia, em particular:

  - Relatórios de resumo/tendências de QoE

  - Relatórios de desempenho de QoE

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Exibir relatórios do servidor de monitoramento

1.  Em um navegador da Web, localize seus servidores que hospedam o SQL Reporting Services.

2.  Exiba os relatórios necessários na tela do navegador.

3.  Adicionais Exporte um relatório selecionando a opção Exportar e o formato de saída necessário.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Configurar a registro de detalhes de chamadas (CDR)

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem permissões equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.

4.  Na página **Registro de Detalhes de Chamada**, clique no site apropriado na tabela, clique em **Editar** e em **Mostrar Detalhes**.

5.  Para ativar a limpeza, selecione **habilitar a limpeza para servidores de monitoramento**.

6.  Em **manter gravações de detalhes da chamada por duração máxima (dias):** selecione o número máximo de dias em que as gravações de detalhes da chamada devem ser mantidas.

7.  Em **Manter dados de relatório de erros por um período máximo de (dias):** selecione o número máximo de dias que os relatórios de erros devem ser retidos.

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="configure-qoe"></a>Configurar QoE

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte Delegate Setup Permissions.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.

4.  Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.

5.  Para ativar a limpeza, selecione **habilitar a limpeza para servidores de monitoramento**.

6.  Em **manter registros de detalhes da chamada por duração máxima (dias):** selecione o número máximo de dias pelos quais os dados de QoE devem ser mantidos.

7.  Clique em Confirmar.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Alterar a política de arquivamento

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.

3.  Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.

4.  Clique em **Global** na lista de políticas, clique em **Editar** e depois em **Mostrar detalhes**.

5.  Em **Editar Política de Arquivamento - Global**, faça o seguinte:

6.  Para habilitar ou desabilitar o arquivamento interno para a implantação, marque ou desmarque a caixa de seleção **arquivar comunicações internas** .

7.  Para habilitar ou desabilitar o arquivamento externo para a implantação, marque ou desmarque a caixa de seleção **arquivar comunicações externas** .

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Aplicar uma política de arquivamento a um usuário

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar o usuário do Lync Server** na **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.

6.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Usar relatórios de monitoramento no Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Relatório de comparação de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

