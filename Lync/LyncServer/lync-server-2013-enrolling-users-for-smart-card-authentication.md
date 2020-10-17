---
title: 'Lync Server 2013: registrar usuários para autenticação de cartão inteligente'
description: 'Lync Server 2013: registrar usuários para autenticação de cartão inteligente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d67994d2152ac344934d093a1b6f7d482a7933a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558467"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Registrar usuários para autenticação de cartão inteligente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-03_

Em geral, há dois métodos para registrar usuários para autenticação de cartão inteligente. O método mais fácil envolve ter os usuários se inscrever diretamente para a autenticação de cartão inteligente usando o registro na Web, enquanto o método mais complexo envolve o uso de um agente de registro. Este tópico se concentra no Autoregistro de certificados de cartão inteligente.

Para obter mais informações sobre o registro em nome de usuários como um agente de registro, consulte registrar-se para certificados em nome de outros usuários em [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) .

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>Para registrar usuários para autenticação de cartão inteligente

1.  Faça logon na estação de trabalho do Windows 8 usando as credenciais de um usuário habilitado para Lync.

2.  Inicie o Internet Explorer.

3.  Navegue até a página **registro da Web da autoridade de certificação** (por exemplo, https://MyCA.contoso.com/certsrv) .
    
    <div>
    

    > [!NOTE]  
    > Se você estiver usando o Internet Explorer 10, talvez seja necessário exibir este site no modo de compatibilidade.

    
    </div>

4.  Na página de **boas-vindas** , selecione **solicitar um certificado**.

5.  Em seguida, selecione **solicitação avançada**.

6.  Selecione **criar e enviar uma solicitação para esta autoridade de certificação**.

7.  Selecione **usuário de cartão inteligente** na seção **modelo de certificado** e conclua a solicitação avançada de certificado com os seguintes valores:
    
      - As **principais opções** confirmam as seguintes configurações:
        
          - Selecione o botão de opção **criar novo conjunto de chaves**
        
          - Para o **CSP**, selecione **Microsoft base cartão inteligente Crypto Provider**
        
          - Para **uso de chave**, selecione **Exchange** (essa é a única opção disponível).
        
          - Em **tamanho da chave**, digite **2048**
        
          - Confirmar se o **nome do contêiner de chave automático** está selecionado
        
          - Deixe as outras caixas desmarcadas.
    
      - Em **Opções adicionais** , confirme os seguintes valores:
        
          - Para o **formato de solicitação** , selecione **CMC**.
        
          - Para **algoritmo de hash** , selecione **SHA1**.
        
          - Para **nome amigável** , insira o **certificado Smardcard**.

8.  Se você estiver usando um leitor de SmartCard físico, insira o cartão inteligente no dispositivo.

9.  Clique em **Enviar** para enviar a solicitação de certificado.

10. Quando solicitado, insira o PIN usado para criar o cartão inteligente virtual.
    
    <div>
    

    > [!NOTE]  
    > O valor padrão de PIN do cartão inteligente virtual é ' 12345678 '.

    
    </div>

11. Depois que o certificado for emitido, clique em **instalar este certificado** para concluir o processo de registro.
    
    <div>
    

    > [!NOTE]  
    > Se a solicitação de certificado falhar com o erro "Este navegador da Web não dá suporte à geração de solicitações de certificado", há três maneiras possíveis de resolver o problema: 
    > <OL>
    > <LI>
    > <P>Habilitar o modo de exibição de compatibilidade no Internet Explorer</P>
    > <LI>
    > <P>Habilitar a opção Ativar configurações da intranet no Internet Explorer</P>
    > <LI>
    > <P>Selecione a configuração redefinir todas as zonas para o nível padrão na guia Segurança no menu opções do Internet Explorer.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

