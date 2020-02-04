---
title: 'Lync Server 2013: usando a autenticação de dois fatores com o cliente Lync'
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
ms.openlocfilehash: 25b5d3305c5d9825342c0293325c9afca96c5a97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a>Usando a autenticação de dois fatores com o Lync Client e o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-11_

Este tópico descreveu como tirar proveito da autenticação de dois fatores com o cliente Lync 2013.

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a>Entrar no Lync 2013 pela primeira vez

Suas informações de entrada do Lync geralmente são configuradas automaticamente quando o Lync 2013 está instalado. Mas, na primeira vez que você usar o Lync, talvez seja necessário iniciar manualmente o cliente.

**Para entrar no Lync pela primeira vez**

1.  Faça logon na rede da sua organização.

2.  Selecione **Iniciar** \> **todos os programas** \> **Microsoft \> Lync Lync 2013**.
    
    Você verá a tela de entrada do Lync.
    
      - Se a caixa de endereço de entrada já estiver preenchida, confirme se o endereço mostrado está correto.
    
      - Se não estiver correto ou se a caixa estiver vazia, insira seu endereço de entrada do Lync (geralmente é o mesmo que o seu endereço de email).
    
      - Se uma caixa de senha vazia for exibida, adicione sua senha.

3.  Selecione **Entrar**.

</div>

<div>

## <a name="sign-out-of-lync"></a>Sair do Lync

Quando terminar de usar o Lync, você pode fechar a exibição, sair da sessão ou sair do programa, tudo a partir do menu arquivo. A tabela a seguir explica as diferenças nas opções.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Opção</th>
<th>O que ela faz</th>
<th>Como executar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fechar</p></td>
<td><p>Fecha a exibição do Lync, mas permite que a sessão do Lync identificada com sua ID de usuário continue sendo executada. Isso acontece para que você possa continuar a obter notificações e a interagir com outras pessoas.</p>
<p>Você pode retomar a exibição a qualquer momento clicando no ícone do Lync na barra de tarefas ou na área de notificação na parte inferior da tela.</p></td>
<td><p>Na janela principal do Lync, siga um destes procedimentos:</p>
<ol>
<li><p>Selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>fechar</strong>.</p></li>
<li><p>Clique no botão <strong>Fechar</strong> (X) no canto superior direito da janela.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>Sair</p></td>
<td><p>Finaliza a sessão do Lync associada à sua ID de usuário, mas o Lync continua a ser executado em segundo plano. Quando você sair, a janela de entrada aparecerá.</p>
<div>

> [!TIP]  
> Selecione <STRONG>Excluir minhas informações de entrada</STRONG> ao sair para remover o registro de sua ID de logon e da senha do computador. Fazer isso torna mais fácil para o pessoal de suporte solucionar problemas de entrada. Também ajuda a garantir que suas informações de entrada fiquem mais seguras ao dificultar que usuários não autorizados façam logon com suas credenciais.


</div></td>
<td><p>Na janela principal do Lync, selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>sair</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Fechar</p></td>
<td><p>Encerra a sessão do Lync e desliga o Lync em seu computador. Depois de sair, se você quiser reiniciar o Lync, selecione <strong>Iniciar</strong> &gt; <strong>todos os programas</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</p></td>
<td><p>Na janela principal do Lync, selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>sair</strong>.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a>Entrar no Lync com um cartão inteligente

Algumas organizações agora usam um processo de entrada em várias etapas, chamado de autenticação de dois fatores, para aumentar a segurança dos usuários do Lync 2013. Se você espera usar esta opção, precisará de um "cartão inteligente" para entrar no Lync. Os cartões inteligentes vêm em duas variedades, físicas e virtuais:

  - **Físico**   sobre o tamanho de um cartão de crédito. Você o insere em um leitor de cartão inteligente ao fazer logon.

  - **Virtual**   não é um objeto físico, mas um identificador eletrônico que é escrito para um chip especial em seu computador, que, em essência, cria o cartão inteligente no seu computador. Disponível somente para uso com computadores com Windows 8 que contenham o chip TPM (Trusted Platform Module).

<div>

## <a name="enroll-your-smart-card"></a>Registrar seu cartão inteligente

Antes que seja possível entrar com um cartão inteligente, o cartão deverá ser "registrado" — ou seja, suas credenciais devem ser identificadas com o cartão. Esse será o caso seja o cartão físico ou virtual. Esse processo já pode ser realizado pelo administrador do Lync Server. Verifique com ele se não tiver certeza se isso foi feito.

<div>


> [!NOTE]  
> Como cada cartão inteligente virtual está associado somente ao dispositivo em que ele está instalado, um cartão separado precisará ser registrado para cada computador com o Windows 8 que você usar.



</div>

**Para registrar manualmente seu cartão inteligente**

1.  Faça logon no computador em que você está executando o Lync.

2.  Usando o Internet Explorer, navegue até a página de Registro da Autoridade de Certificação da sua organização.
    
    Pergunte ao administrador do Lync Server o endereço Web desse recurso, se ainda não o tiver. A URL terá a seguinte aparência: https://MyCA.\[nomedesuaempresa\]. com/certsrv.
    
    <div>
    

    > [!NOTE]  
    > Se você estiver usando o Internet Explorer 10, talvez precise exibir o site em Modo de Compatibilidade.

    
    </div>

3.  Quando solicitado a fazer logon na página de certificação, faça logon usando sua conta de domínio (em vez do administrador do seu computador).

4.  Na página de Boas-vindas do site, selecione **Solicitar um certificado**.

5.  Selecione **Solicitação Avançada**.

6.  Selecione **Criar e enviar uma solicitação para esta CA** e clique em **Avançar**.

7.  Agora você verá uma página chamada Estação de Registro de Cartão Inteligente. Aprove a solicitação para instalar o controle ActiveX e então preencha o formulário Solicitação de Certificado Avançado desta forma:
    
    1.  Selecione **Usuário de cartão inteligente** na lista suspensa **Modelo de Certificado**.
    
    2.  Selecione **Criar novo conjunto de chaves**.
    
    3.  Localize as informações do fabricante no rótulo do seu cartão inteligente e selecione esse fabricante na lista suspensa **CSP**.
    
    4.  Selecione **CSP** como o Formato de Solicitação, caso ainda não esteja selecionado.
    
    5.  Selecione **sha1** na lista suspensa Algoritmo de Hash, caso ainda não tenha sido selecionado.
    
    6.  Dê um nome ao seu certificado que seja fácil de reconhecer e clique em **Enviar**.

8.  Agora insira seu cartão inteligente em branco no leitor de cartão conectado à estação de registro e clique em **Registrar**.

9.  Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se o encarregado do suporte técnico não tiver dado um PIN para você registrar seu cartão inteligente, use o valor padrão de PIN de cartão inteligente, 12345678.

    
    </div>

10. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez em que o cartão inteligente for usado.

11. Agora insira seu cartão inteligente em branco no leitor de cartão conectado à estação de registro e clique em **Registrar**.

12. Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se o encarregado do suporte técnico não tiver dado um PIN para você registrar seu cartão inteligente, use o valor padrão de PIN de cartão inteligente, 12345678.

    
    </div>

13. Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez em que o cartão inteligente for usado.

14. Clique em **OK** para confirmar se o certificado exibido tem suas informações neles.

15. Assim que for exibido o aviso de que o certificado foi emitido, clique em **Instalar este certificado** para concluir o processo de registro.

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a>Entre no Lync com as credenciais do seu cartão inteligente

Antes de usar o cartão inteligente pela primeira vez, é recomendável clicar em **excluir minhas informações de entrada** na página de entrada do Lync. Fazer isso limpará qualquer credencial de entrada armazenada no computador e eliminará uma possível origem de erros.

**Para entrar no Lync com as credenciais do seu cartão inteligente**

1.  Inicie o cliente do Lync.

2.  Na tela Entrar, digite seu nome de conta de usuário na caixa **Endereço de entrada** e clique em **Entrar**.

3.  Se você estiver usando um cartão inteligente virtual, ignore esta etapa.
    
    Se estiver usando um cartão inteligente físico, insira o cartão inteligente no leitor de cartão inteligente quando solicitado e então clique em **OK** quando o cartão for detectado.

4.  Digite o número PIN do seu cartão inteligente e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se você não tiver recebido um número PIN de cartão inteligente do pessoal de suporte, use o valor padrão, que é 12345678.

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

