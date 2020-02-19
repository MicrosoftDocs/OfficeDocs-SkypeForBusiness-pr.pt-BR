---
title: Configurar monitoramento do SCOM
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
ms.openlocfilehash: 73fccbc093365565fdc4062715b517e62eed3e7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>Configurar monitoramento do SCOM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Após a migração para o Microsoft Lync Server 2013, você deve concluir algumas tarefas para configurar o Lync Server 2013 para trabalhar com o System Center Operations Manager.

  - Aplicar atualizações do Lync Server 2010 a um servidor escolhido para gerenciar a lógica de descoberta central.

  - Atualize a chave de registro do servidor candidato a descoberta central.

  - Configure seu servidor de gerenciamento do System Center Operations Manager principal para substituir o nó de descoberta central de candidatos.

Instruções para executar cada uma dessas tarefas são fornecidas abaixo.

**Aplicar atualizações do Lync Server 2010 a um servidor escolhido para gerenciar a lógica de descoberta central.**

1.  Eleja um servidor que possua os arquivos do agente do Gerenciador de Operações do Sistema Central instalados e esteja configurado como nó de descoberta central.

2.  Aplicar atualizações do Lync Server 2010 a este servidor. Consulte o tópico [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).

**Atualize a chave de registro do servidor candidato a descoberta central.**

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
    > Sempre que você editar o registro, você poderá receber um erro em que o comando falha caso a chave de registro já exista. Caso isso aconteça, você pode ignorar com segurança o erro.

    
    </div>

**Configure seu servidor de gerenciamento do System Center Operations Manager principal para substituir o nó do Inspetor de descoberta central de candidatos.**

1.  Em um computador onde o console do Gerenciador de Operações do  System Center foi instalado, expanda **Objetos do Pacote de Gerenciamento** e selecione **Descobertas de Objeto**.

2.  Clique em **Alterar escopo...**

3.  Da página **Escopo de Objetos do Pacote de Gerenciamento**, selecione **Candidato a Descoberta LS**.

4.  Substitua o **Valor Efetivo de Candidato a Descoberta LS** para o nome do servidor de candidato eleito para o procedimento anterior.

Por fim, finalize as alterações, reinicie o serviço de integridade no Servidor de Gerenciamento de Raiz de Gerenciamento de Operações do System Center.

</div>

<span> </span>

</div>

</div>

</div>

