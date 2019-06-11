---
title: 'Lync Server 2013: Configurando o Windows 8 para cartões inteligentes virtuais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Configurar o Windows 8 para usar cartões inteligentes virtuais com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-03_

Um fator que deve ser levado em consideração na implantação da autenticação de dois fatores e na tecnologia de cartão inteligente é o custo da implementação. O Windows 8 fornece vários recursos de segurança novos, e um dos novos recursos mais interessantes é o suporte para cartões inteligentes virtuais.

Para computadores que contam com um chip Trusted Platform Module (TPM) compatível com a especificação da versão 1.2, as organizações podem agora se beneficiar do logon com cartões inteligentes sem fazer mais nenhum investimento em hardware. Para obter mais informações, consulte usando cartões inteligentes virtuais com o Windows [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)8 em.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar o Windows 8 para cartões inteligentes virtuais

1.  Faça logon no computador com o Windows 8 usando as credenciais de um usuário compatível com o Lync.

2.  Na tela Iniciar do Windows 8, mova seu cursor para o canto inferior direito da tela.

3.  Selecione a opção **Pesquisar** e pesquise **Command Prompt**.

4.  Clique com o botão direito do mouse em **Prompt de comando** e selecione **Executar como administrador**.

5.  Abra o Console de Gerenciamento do Trusted Platform Module (TPM) executando o seguinte comando:
    
        Tpm.msc

6.  No Console de Gerenciamento do TPM, confira se a versão do seu TPM é 1.2 ou superior.
    
    <div>
    

    > [!NOTE]  
    > Caso surja uma caixa de diálogo com a mensagem de que não foi possível encontrar o Trust Platform Module (TPM) compatível, verifique se o computador tem um módulo TPM compatível e se ele está habilitado na BIOS do sistema.

    
    </div>

7.  Feche o Console de Gerenciamento do TPM

8.  No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Para personalizar o valor do PIN ao criar o cartão inteligente virtual, use o prompt /pin.

    
    </div>

9.  No prompt de comando, abre o Console de Gerenciamento do computador executando o seguinte comando:
    
        CompMgmt.msc

10. No Console de Gerenciamento do computador, selecione **Gerenciamento de Dispositivos**.

11. Expanda **Leitores de cartão inteligente**.

12. Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

