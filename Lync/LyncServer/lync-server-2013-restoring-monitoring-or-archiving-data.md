---
title: 'Lync Server 2013: restaurando dados de monitoramento ou arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5be8d5409a5770ef2ee928075c147c126ce4219a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Restauração de dados de monitoramento ou arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-18_

A restauração de dados de monitoramento e arquivamento não é necessária para que o Lync Server fique ativo e em execução após uma falha. No entanto, se os dados de monitoramento e arquivamento forem críticos para sua organização, você desejará restaurar os dados após recriar os bancos de dados.

O procedimento a seguir descreve como usar o SQL Server Management Studio para restaurar os dados de arquivamento ou monitoramento.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>Para restaurar os dados de monitoramento ou arquivamento de um arquivo de backup

1.  Faça logon no servidor que você está restaurando como um membro do grupo Administradores no computador local ou em um grupo com direitos de usuário equivalentes.

2.  Abra o SQL Server Management Studio: clique em **Iniciar**, em **todos os programas**, em **Microsoft SQL Server 2012** ou **Microsoft SQL Server 2008 R2**e, em seguida, clique em **SQL Server Management Studio**.

3.  Em **Conectar ao Servidor**, conecte-se à instância de SQL Server fornecendo pelo menos o nome do servidor e as informações de autenticação.

4.  Em **Pesquisador de Objetos**, clique com o botão direito do mouse em **Bancos de dados** e clique em **Restaurar Banco de Dados**.

5.  Em **Selecionar uma página**, clique em **Geral** e selecione o nome do banco de dados em **Para o banco de dados** da seguinte maneira:
    
      - Para um banco de dados de arquivamento, selecione **LcsLog**.
    
      - Para um banco de dados CDR (gravação de detalhes de chamada), selecione **LcsCDR**.
    
      - Para um banco de dados QoE (Qualidade da Experiência), selecione **QoEMetrics**.

6.  Clique em **Do dispositivo**.

7.  Em **Selecione os conjuntos de backup a serem restaurados**, clique no arquivo de backup e clique em **Restaurar**.

8.  Em **Selecionar uma página**, clique em **Opções**, verifique se o caminho do arquivo de dados e o caminho de log estão na pasta correta e clique em **OK**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Para garantir que as listas de controle de acesso (ACLs) estejam corretas

1.  Expanda **Bancos de dados**, expanda o banco de dados de arquivamento ou monitoramento, expanda **Segurança** e expanda **Usuários**.

2.  Verifique se o grupo de domínio RTCComponentUniversalServices existe como um usuário.

3.  Se o RTCComponentUniversalServices não existir nos **usuários**, faça o seguinte:
    
    1.  Clique com o botão direito do mouse em **Usuários** e clique em **Novo Usuário**.
    
    2.  Em **nome de logon**, digite o nome do grupo ausente, RTCComponentUniversalServices.
    
    3.  Em **Associação à função de banco de dados**, selecione a permissão **ServerRole** e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Não é necessário reiniciar o serviço de arquivamento ou monitoramento.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

