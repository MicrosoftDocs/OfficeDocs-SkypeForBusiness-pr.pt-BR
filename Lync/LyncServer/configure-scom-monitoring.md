---
title: Configurar monitoramento SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7904edf9723dacdd28f69a75bec17cb5db3c2061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>Configurar monitoramento SCOM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Depois de migrar para o Microsoft Lync Server 2013, você deve concluir algumas tarefas para configurar o Lync Server 2013 para trabalhar com o System Center Operations Manager.

  - Aplicar atualizações do Lync Server 2010 a um servidor escolhido para gerenciar a lógica de descoberta central.

  - Atualize a chave do registro do servidor candidato à descoberta central.

  - Configure o servidor de gerenciamento principal do System Center Operations Manager para substituir o nó de descoberta central de candidatos.

As instruções para executar cada uma dessas tarefas são fornecidas abaixo.

**Aplicar atualizações do Lync Server 2010 a um servidor escolhido para gerenciar a lógica de descoberta central.**

1.  Escolha um servidor que tenha os arquivos de agente do System Center Operations Manager instalados e esteja configurado como um nó de descoberta de candidatos.

2.  Aplicar atualizações do Lync Server 2010 a este servidor. Consulte o tópico [aplicar atualizações do Lync Server 2010](apply-lync-server-2010-updates.md).

**Atualize a chave do registro do servidor candidato à descoberta central.**

1.  No servidor escolhido para gerenciar a lógica de descoberta central, abra uma janela de comando do Windows PowerShell.

2.  Na linha de comando, digite o seguinte:
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Sempre que você edita o registro, pode ocorrer um erro inque o comando falhou se a chave do registro já existe. Se isso acontecer, você pode ignorar o erro com segurança.

    
    </div>

**Configure o servidor de gerenciamento principal do System Center Operations Manager para substituir o nó do inspetor da descoberta do candidato.**

1.  Em um computador em que o console System Center Operations Manager foi instalado, expanda os **objetos do pacote de gerenciamento** e selecione descobertas de **objetos**.

2.  Clique em **alterar escopo..** .

3.  Na página **objetos do pacote de gerenciamento de escopo** , selecione **candidato para descoberta ls**.

4.  Substitua o **valor efetivo de candidato à descoberta ls** pelo nome do servidor de candidatos escolhido no procedimento anterior.

Por fim, para finalizar suas alterações, reinicie o serviço de integridade no servidor de gerenciamento raiz do System Center Operations Manager.

</div>

<span> </span>

</div>

</div>

</div>

