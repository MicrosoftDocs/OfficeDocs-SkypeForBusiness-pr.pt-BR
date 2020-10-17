---
title: 'Lync Server 2013: Implantando pools front-end emparelhados para recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309c8f7ac7da4e40f2b16e5d13015330b2d9b611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514518"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Implantando pools front-end emparelhados para recuperação de desastre no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Você pode implantar facilmente a topologia de recuperação de desastres dos pools de front-ends emparelhados usando o construtor de topologias.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>Para implantar um par de pools do Front-End

1.  Se os pools são novos e ainda não foram definidos, use o construtor de topologias para criar os pools.

2.  No construtor de topologias, clique com o botão direito do mouse em um dos dois pools e clique em **Editar propriedades**.

3.  Clique em **Resiliência** no painel esquerdo e selecione **Pool de backup associado** no painel direito.

4.  Na caixa abaixo **Pool de backup associado**, selecione o pool que você deseja emparelhar com este pool. Apenas pools existentes que não estão emparelhados com outro pool estarão disponíveis para selecionar.
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  Selecione **Failover automático e failback para voz** e clique em **OK**.
    
    Ao exibir os detalhes sobre este pool, o pool associado agora aparece no painel direito em **Resiliência**.

6.  Use o construtor de topologias para publicar a topologia.

7.  Se os dois pools ainda não foram implantados, implante-os e a configuração estará concluída. É possível pular as duas etapas finais neste procedimento.
    
    No entanto, se os pools já foram implantados antes de você definir a relação emparelhada, você deve concluir as seguintes duas etapas finais.

8.  Em cada Servidor de Front-End Server nos pools, execute o seguinte:
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    Isto configura outros serviços necessários para que o emparelhamento de backup funcione corretamente.

9.  Em um prompt de comando do Shell de gerenciamento do Lync Server, execute o seguinte:
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. Force o usuário e os dados de conferência de ambos os pools para sincronização um com o outro, com os seguintes cmdlets:
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    Sincronizar os dados pode levar algum tempo. É possível usar os seguintes cmdlets para verificar os tatus. Certifique-se de que o status em ambas as direções está no estado Steady.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> A opção <STRONG>failover automático e failback para voz</STRONG> e os intervalos de tempo associados no construtor de topologia só se aplicam aos recursos de resiliência de voz introduzidos no Lync Server 2010. Selecionar esta opção não implica que o failover de pool discutido neste documento seja automático. O failover de pool e failback sempre exige que um administrador invoque manualmente os cmdlets de failover e failback, respectivamente.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

