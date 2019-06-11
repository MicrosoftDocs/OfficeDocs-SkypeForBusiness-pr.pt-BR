---
title: 'Lync Server 2013: restaurar dados de monitoramento ou arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 803cb6050d4230653a13f1e3e66c2a092911c509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Restaurando o monitoramento ou arquivando dados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-18_

Não é necessário restaurar os dados de monitoramento e arquivamento para colocar o Lync Server em funcionamento após uma falha. No entanto, se o monitoramento e o arquivamento de dados forem críticos para a sua organização, você desejará restaurar os dados após recriar os bancos de dados.

O procedimento a seguir descreve como usar o SQL Server Management Studio para restaurar o arquivamento ou o monitoramento de dados.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>Para restaurar o monitoramento ou o arquivamento de dados de um arquivo de backup

1.  Faça logon no servidor que você está restaurando como membro do grupo Administradores no computador local ou em um grupo com direitos de usuário equivalentes.

2.  Abra o SQL Server Management Studio: clique em **Iniciar**, em **todos os programas**, em **Microsoft SQL Server 2012** ou **Microsoft SQL Server 2008 R2**e, em seguida, clique em **SQL Server Management Studio**.

3.  Em **conectar-se ao servidor**, conecte-se à instância do SQL Server fornecendo pelo menos o nome do servidor e as informações de autenticação.

4.  No **Explorador de objetos**, clique com o botão direito do mouse em **bancos**de dados e clique em **restaurar banco de dados**.

5.  Em **Selecione uma página**, clique em **geral**e, em seguida, no **banco de dados** , selecione o nome do banco de dados da seguinte maneira:
    
      - Para um banco de dados de arquivamento, selecione **LcsLog**.
    
      - Para um banco de dados do recurso de gravação de detalhes de chamadas (CDR), selecione **LcsCDR**.
    
      - Para um banco de dados de qualidade da experiência (QoE), selecione **QoEMetrics**.

6.  Clique em **do dispositivo**.

7.  Em **Selecione os conjuntos de backup a serem restaurados**, clique no arquivo de backup e, em seguida, clique em **restaurar**.

8.  Em **Selecione uma página**, clique em **Opções**, verifique se o caminho do arquivo de dados e o caminho do log estão na pasta correta e clique em **OK**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Para garantir que as listas de controle de acesso (ACLs) estejam corretas

1.  Expanda **bancos**de dados, expanda o arquivo de arquivamento ou monitoramento, expanda **segurança**e, em seguida, expanda **usuários**.

2.  Verifique se o grupo de domínio RTCComponentUniversalServices existe como usuário.

3.  Se RTCComponentUniversalServices não existir em **usuários**, faça o seguinte:
    
    1.  Clique com o botão direito do mouse em **usuários**e, em seguida, clique em **novo usuário**.
    
    2.  Em **nome de logon**, digite o nome do grupo ausente, RTCComponentUniversalServices.
    
    3.  Em **Associação de função de banco de dados**, selecione a permissão **ServerRole** e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Você não precisa reiniciar o serviço de arquivamento ou monitoramento.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

