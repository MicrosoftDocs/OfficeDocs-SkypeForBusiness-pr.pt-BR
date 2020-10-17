---
title: 'Lync Server 2013: usando autenticação de dois fatores com o cliente Lync'
description: 'Lync Server 2013: usando autenticação de dois fatores com o cliente Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfde1d04d4e641c8fbe4817ffce214df891b565
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547277"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Usando a autenticação de dois fatores com o Lync Client e o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-11_

Este tópico descreveu como aproveitar a autenticação de dois fatores com o cliente Lync 2013.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Entrar no Lync 2013 pela primeira vez

Suas informações de entrada do Lync geralmente são configuradas automaticamente quando o Lync 2013 é instalado. Mas, na primeira vez que você usar o Lync, talvez seja necessário iniciar manualmente o cliente.

**Para entrar no Lync pela primeira vez**

1.  Faça logon na rede da sua organização.

2.  Selecione **Iniciar** \> **todos os programas** \> **Microsoft Lync \> Lync 2013**.
    
    Você deve ver a tela de entrada do Lync.
    
      - Se a caixa endereço de entrada já estiver preenchida, confirme se o endereço mostrado está correto.
    
      - Se ele não estiver correto, ou se a caixa estiver vazia, insira seu endereço de entrada do Lync (geralmente é o mesmo que seu endereço de email).
    
      - Se uma caixa de senha vazia for exibida, adicione sua senha.

3.  Selecione **entrar**.

</div>

<div>

## <a name="sign-out-of-lync"></a>Sair do Lync

Quando terminar de usar o Lync, você poderá fechar a exibição, sair da sessão ou sair do programa, tudo a partir do menu arquivo. A tabela a seguir explica as diferenças nas opções.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Opção</th>
<th>Função</th>
<th>Como realizá-lo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fechar</p></td>
<td><p>Fecha a tela do Lync, mas permite que a sessão do Lync identificada com sua ID de usuário continue a ser executada. Isso é feito para que você possa continuar a receber notificações e interagir com outras pessoas.</p>
<p>Você pode obter novamente a exibição a qualquer momento clicando no ícone do Lync na barra de tarefas ou na área de notificação na parte inferior da tela.</p></td>
<td><p>Na janela principal do Lync, siga um destes procedimentos:</p>
<ol>
<li><p>Selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>fechar</strong>.</p></li>
<li><p>Clique no botão <strong>fechar</strong> (X) no canto superior direito da janela.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Sair</p></td>
<td><p>Encerra a sessão do Lync associada à sua ID de usuário, mas o Lync continua a ser executado em segundo plano. Quando você sair, a janela de entrada será exibida.</p>
<div>

> [!TIP]  
> Selecione <STRONG>excluir minhas informações de entrada</STRONG> ao sair para remover o registro de sua ID de logon e senha do computador. Isso pode tornar mais fácil para as pessoas de suporte solucionar problemas de entrada. Também pode ajudar a garantir que as informações de entrada sejam mais seguras, tornando difícil para os usuários não autorizados fazer logon com suas credenciais.


</div></td>
<td><p>Na janela principal do Lync, selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>sair</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Sair</p></td>
<td><p>Encerra a sessão do Lync e desliga o Lync no seu computador. Após sair, se você quiser reiniciar o Lync, selecione <strong>Iniciar</strong> &gt; <strong>todos os programas</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>Na janela principal do Lync, selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>sair</strong>.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Entrar no Lync com um cartão inteligente

Algumas organizações agora usam um processo de entrada em várias etapas, chamado de autenticação de dois fatores, para aumentar a segurança dos seus usuários do Lync 2013. Se você espera usar essa opção, precisará de um "cartão inteligente" para entrar no Lync. Os cartões inteligentes vêm em duas variedades, físico e virtual:

  - **Físico**     Sobre o tamanho de um cartão de crédito. Você o insere em um leitor de cartão inteligente ao fazer logon.

  - **Virtual**     Não é um objeto físico, mas um identificador eletrônico que é gravado em um chip especial no computador, que, em essência, cria o cartão inteligente em seu computador. Disponível somente para uso com computadores com Windows 8 que contenham o chip TPM (Trusted Platform Module).

<div>

## <a name="enroll-your-smart-card"></a>Registrar seu cartão inteligente

Para que você possa entrar com um cartão inteligente, o cartão deve ser "inscrito", ou seja, suas credenciais de usuário devem ser identificadas com o cartão. Esse é o caso se o cartão for físico ou virtual. Esse processo já pode ter sido realizado pelo administrador do Lync Server. Verifique com eles se você não tiver certeza se isso foi feito.

<div>


> [!NOTE]  
> Como cada cartão inteligente virtual é associado apenas ao dispositivo em que ele está instalado, um cartão separado precisará ser inscrito para cada computador com o Windows 8 que você usa.



</div>

**Para registrar manualmente seu cartão inteligente**

1.  Faça logon no computador em que você executará o Lync.

2.  Usando o Internet Explorer, navegue até a página registro da Web da autoridade de certificação da sua organização.
    
    Pergunte ao administrador do Lync Server pelo endereço da Web desse recurso se você ainda não o tiver. A URL se parecerá com esta: https://MyCA.\ [Yourcompanyname \] . com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Se você estiver usando o Internet Explorer 10, talvez seja necessário exibir este site no modo de compatibilidade.

    
    </div>

3.  Quando for solicitado a fazer logon na página de certificação, faça logon usando sua conta de domínio (em vez de como administrador do seu computador).

4.  Na página de boas-vindas do site, selecione **solicitar um certificado**.

5.  Selecione **solicitação avançada**.

6.  Selecione **criar e enviar uma solicitação para esta autoridade de certificação**e clique em **Avançar**.

7.  Agora você verá uma página chamada Estação de registro de cartão inteligente. Aprove a solicitação para instalar o controle ActiveX e preencha o formulário de solicitação de certificado avançado da seguinte maneira:
    
    1.  Selecione **usuário de cartão inteligente** na lista suspensa **modelo de certificado** .
    
    2.  Selecione **criar novo conjunto de chaves**.
    
    3.  Encontre as informações do fabricante no rótulo do seu cartão inteligente e selecione o fabricante na lista suspensa **CSP** .
    
    4.  Selecione **CSP** como o formato de solicitação, se ainda não estiver selecionado.
    
    5.  Selecione **SHA1** na lista suspensa algoritmo de hash, se ainda não estiver selecionada.
    
    6.  Dê um nome ao seu certificado, que você reconhecerá e clique em **Enviar**.

8.  Agora insira o cartão inteligente em branco no leitor de cartão anexado à estação de registro e clique em **registrar**.

9.  Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se sua pessoa de suporte técnico não tiver dado a você um PIN especial a ser usado para registrar seu cartão inteligente, use o valor padrão de PIN do cartão inteligente, que é 12345678.

    
    </div>

10. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez que o cartão inteligente for usado.

11. Agora insira o cartão inteligente em branco no leitor de cartão anexado à estação de registro e clique em **registrar**.

12. Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se sua pessoa de suporte técnico não tiver dado a você um PIN especial a ser usado para registrar seu cartão inteligente, use o valor padrão de PIN do cartão inteligente, que é 12345678.

    
    </div>

13. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez que o cartão inteligente for usado.

14. Clique em **OK** para confirmar que o certificado exibido tem suas informações nele.

15. Após ver o aviso de que o certificado foi emitido, clique em **instalar este certificado** para concluir o processo de registro.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Entrar no Lync com suas credenciais de cartão inteligente

Antes de usar o cartão inteligente pela primeira vez, é recomendável clicar em **excluir minhas informações de entrada** na página de entrada do Lync. Isso limpa as credenciais de entrada armazenadas no computador e elimina uma possível fonte de erro.

**Para entrar no Lync com suas credenciais de cartão inteligente**

1.  Inicie o cliente do Lync.

2.  Na tela de entrada, digite o nome da conta de usuário de entrada na caixa **endereço de entrada** e clique em **entrar**.

3.  Se você estiver usando um cartão inteligente virtual, pule esta etapa.
    
    Se você estiver usando um cartão inteligente físico, insira o cartão inteligente no leitor de cartão inteligente e, em seguida, clique em **OK** quando o cartão for detectado.

4.  Digite o número PIN do cartão inteligente e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se você não recebeu um número PIN de cartão inteligente pelo pessoal de suporte, use o valor padrão, que é 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

