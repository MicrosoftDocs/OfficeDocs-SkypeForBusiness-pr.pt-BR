---
title: 'Lync Server 2013: registrando usuários para autenticação de cartão inteligente'
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
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Registrar usuários para autenticação de cartão inteligente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-03_

Em geral, há dois métodos para registrar usuários para autenticação de cartão inteligente. O método mais fácil envolve ter usuários registrados diretamente para autenticação de cartão inteligente usando o registro via Web, enquanto o método mais complexo envolve o uso de um agente de registro. Este tópico se concentra no autorregistro para certificados de cartões inteligentes.

Para obter mais informações sobre como registrar-se em nome dos usuários como um agente de inscrição, consulte registrar-se para obter certificados [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)em nome de outros usuários em.

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>Para registrar usuários para autenticação de cartão inteligente

1.  Faça logon na estação de trabalho do Windows 8 usando as credenciais de um usuário compatível com o Lync.

2.  Inicie o Internet Explorer.

3.  Navegue até a página de **registro na Web da autoridade** de https://MyCA.contoso.com/certsrv)certificação (por exemplo,.
    
    <div>
    

    > [!NOTE]  
    > Caso esteja usando o Internet Explorer 10, pode ser necessário visualizar esta página em Modo de Compatibilidade.

    
    </div>

4.  Na **Página Inicial**, selecione **Solicitar um certificado**.

5.  Em seguida, selecione **Solicitação Avançada**.

6.  Selecione **Criar e enviar uma solicitação para esta autoridade de certificação**.

7.  Selecione **Usuário do Cartão Inteligente** na seção **Modelo de Certificado** e preencha a solicitação de certificado avançado com os seguintes valores:
    
      - As **Opções de Chave** confirmam as seguintes configurações:
        
          - Selecione o botão de opção **Criar novo conjunto de chaves**
        
          - Em **CSP**, selecione **Microsoft Base Smart Card Crypto Provider**
        
          - Em **Uso da Chave**, selecione **Exchange** (é a única opção disponível).
        
          - Em **Tamanho da Chave**, digite **2048**
        
          - Confirme se a opção **Nome de contêiner de chave automático** está selecionada
        
          - Deixe as outras caixas desmarcadas.
    
      - Em **Opções Adicionais**, confirme os seguintes valores:
        
          - Em **Formato da Solicitação**, selecione **CMC**.
        
          - Em **Algoritmo de Hash**, selecione **sha1**.
        
          - Em **Nome Amigável**, digite **Smardcard Certificate**.

8.  Caso você esteja usando um leitor de cartão inteligente físico, insira o cartão inteligente no dispositivo.

9.  Clique em **Enviar** para enviar a solicitação do certificado.

10. Quando solicitado, digite o PIN usado para criar o cartão inteligente virtual.
    
    <div>
    

    > [!NOTE]  
    > O PIN padrão do cartão inteligente virtual é ‘12345678’.

    
    </div>

11. Depois que o certificado tiver sido emitido, clique em **Instalar este certificado** para concluir o processo de registro.
    
    <div>
    

    > [!NOTE]  
    > Caso sua solicitação de certificado falhe com o erro “Este navegador da Web não dá suporte à geração de solicitações de certificados”, há três maneiras possíveis para resolver o problema: 
    > <OL>
    > <LI>
    > <P>Habilitar o Modo de Exibição de Compatibilidade no Internet Explorer</P>
    > <LI>
    > <P>Habilitar a opção Ativar configurações de Intranet no Internet Explorer</P>
    > <LI>
    > <P>Selecionar a configuração Restaurar o nível padrão de todas as zonas na guia Segurança no menu de opções do Internet Explorer.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

