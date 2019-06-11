---
title: 'Lync Server 2013: especificando a retenção de dados de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae725c58f3b93c7e3b267eec105571f8bbf882ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a>Especificando a retenção de dados de CDR no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Por padrão, os dados de CDR (registro de detalhes das chamadas) são purgados após 60 dias. É possível usar as configurações da página **Registro de Detalhes das Chamadas** para manter os dados por um período maior ou menor. Se você desabilitar o CDR, os dados que foram capturados antes da desabilitação do CDR também poderão ser purgados.

<div>


> [!NOTE]  
> Você deve configurar o CDR e a QoE (Qualidade da Experiência) para reter os dados durante o mesmo número de dias. Cada chamada nos CDRs (relatórios de detalhes de chamada), disponível na página da web de Relatórios do Monitoring Serve, inclui informações de CDR e QoE. Se a duração da limpeza de CDR e QoE for diferente, algumas chamadas poderão incluir apenas dados de CDR, enquanto outras poderão incluir apenas dados de QoE.



</div>

Use o procedimento a seguir para definir as configurações de limpeza de dados de CDR.

<div>

## <a name="to-specify-retention-of-cdr-data"></a>Para especificar a retenção de dados de CDR

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.

4.  Na página **Registro de Detalhes de Chamada**, clique no site apropriado na tabela, clique em **Editar** e em **Mostrar Detalhes**.

5.  Para ativar a limpeza, selecione **Habilitar limpeza CDRs**.

6.  Em **Manter CDRs por um período máximo (dias):** selecione o número máximo de dias que os registros de detalhes de chamada devem ser retidos.

7.  Em **Manter dados de relatório de erros por um período máximo de (dias):** selecione o número máximo de dias que os relatórios de erros devem ser retidos.

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Especificando a retenção de CDR usando cmdlets do Windows PowerShell

Você pode criar configurações de retenção de CDR usando o Windows PowerShell e o cmdlet Set-CsCdrConfiguration. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a>Para especificar a retenção de CDR para um local específico

  - Este comando habilita a exclusão de dados CDR para o local Redmond e configura o local para manter os dados CDR e os dados do relatório de erro por 20 dias.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a>Para especificar a retenção CDR para vários locais

  - Este comando configura a retenção CDR para todas as definições de configuração CDR em uso em uma organização.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Registro de detalhes de chamadas (CDR) no Lync Server 2013](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

