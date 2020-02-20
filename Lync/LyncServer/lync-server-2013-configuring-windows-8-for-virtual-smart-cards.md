---
title: 'Lync Server 2013: Configurando o Windows 8 para cartões inteligentes virtuais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29fa0be32f5a2c2a0af0b63dadddda3038675adf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Configurando o Windows 8 para o uso de cartões inteligentes virtuais com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-03_

Um fator a ser considerado ao implantar a autenticação de dois fatores e a tecnologia de cartão inteligente é o custo da implementação. O Windows 8 oferece vários recursos de segurança novos e um dos novos recursos mais interessantes é o suporte para cartões inteligentes virtuais.

Para computadores equipados com um chip TPM (Trusted Platform Module) que atende à versão 1,2 da especificação, as organizações agora podem obter os benefícios do logon do cartão inteligente sem fazer investimentos adicionais em hardware. Para obter mais informações, consulte usando cartões inteligentes virtuais com o Windows [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365)8 em.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Para configurar o Windows 8 para cartões inteligentes virtuais

1.  Faça logon no computador com o Windows 8 usando as credenciais de um usuário habilitado para Lync.

2.  Na tela inicial do Windows 8, mova o cursor para o canto inferior direito da tela.

3.  Selecione a opção de **pesquisa** e procure o **prompt de comando**.

4.  Clique com o botão direito do mouse em **prompt de comando**e selecione **Executar como administrador**.

5.  Abra o console de gerenciamento do Trusted Platform Module (TPM) executando o seguinte comando:
    
        Tpm.msc

6.  No console de gerenciamento do TPM, verifique se a versão de especificação do TPM é pelo menos 1,2
    
    <div>
    

    > [!NOTE]  
    > Se você receber uma caixa de diálogo informando que um módulo de plataforma de confiança (TPM) compatível não pode ser encontrado, verifique se o computador tem um módulo TPM compatível e se está habilitado no BIOS do sistema.

    
    </div>

7.  Fechar o console de gerenciamento do TPM

8.  No prompt de comando, crie um novo cartão inteligente virtual usando o seguinte comando:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Para fornecer um valor de PIN personalizado ao criar o cartão inteligente virtual, use o prompt/PIN em vez disso.

    
    </div>

9.  No prompt de comando, abra o console de gerenciamento do computador executando o seguinte comando:
    
        CompMgmt.msc

10. No console de gerenciamento do computador, selecione **Gerenciamento de dispositivo**.

11. Expanda **leitores de cartões inteligentes**.

12. Verifique se o novo leitor de cartão inteligente virtual foi criado com êxito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

