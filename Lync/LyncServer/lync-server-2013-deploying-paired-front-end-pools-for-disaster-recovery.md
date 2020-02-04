---
title: 'Lync Server 2013: Implantando pools Front-End emparelhados para recuperação de desastre'
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
ms.openlocfilehash: d264128a7fef38fd220d2527772d6065dca7c964
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Implantando pools Front-End emparelhados para recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Você pode implantar facilmente a topologia de recuperação de desastres de pools front-end em par usando o construtor de topologias.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>Para implantar um par de pools de front-ends

1.  Se os pools forem novos e ainda não estiverem definidos, use o construtor de topologias para criar os grupos.

2.  No construtor de topologias, clique com o botão direito do mouse em um dos dois grupos e clique em **Editar propriedades**.

3.  Clique em **Resiliência** no painel esquerdo e selecione **Pool de Backup Associado** no painel direito.

4.  Na caixa abaixo de **Pool de Backup Associado**, selecione o pool que você deseja emparelhar com este pool. Apenas pools existentes que não estejam emparelhados com outro pool estarão disponíveis para seleção.
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  Selecione **Failback e failover automático para Voz** e clique em **OK**.
    
    Quando você exibir os detalhes sobre este pool, o pool associado agora aparecerá no painel direito em **Resiliência**. 

6.  Use o construtor de topologias para publicar a topologia.

7.  Se os dois pools ainda não foram implantados, implante-os e a configuração estará concluída. Você pode ignorar as duas etapas finais deste procedimento.
    
    No entanto, se os pools já foram implantados antes de você definir a relação emparelhada, você deverá concluir as duas etapas finais a seguir.

8.  Em cada Servidor Front-End nos pools, execute o seguinte:
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    Isso configura outros serviços necessários para que o emparelhamento de backup funcione corretamente.

9.  Em um prompt de comando do Shell de gerenciamento do Lync Server, execute o seguinte:
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. Force a sincronização dos dados do usuário e de conferência de ambos os pools com os seguintes cmdlets:
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    A sincronização dos dados pode levar algum tempo. É possível usar os cmdlets a seguir para verificar o status. O status em ambas as direções deve estar em um estado estável.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> A opção <STRONG>failover automático e failback para voz</STRONG> e os intervalos de tempo associados no construtor de topologia só se aplicam aos recursos de resiliência de voz que foram introduzidos no Lync Server 2010. Selecionar essa opção não implica que o failover de pool discutido neste documento seja automático. O failback e o failover de pool sempre exigem que um administrador invoque manualmente os cmdlets de failback e failover, respectivamente.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

