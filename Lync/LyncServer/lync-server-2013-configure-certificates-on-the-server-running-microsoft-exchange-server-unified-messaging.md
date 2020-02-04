---
title: 'Lync Server 2013: configurar certificados no servidor que executa o Microsoft Exchange Server Unified Messaging'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d31ed8b750d0162a2c09d49ca8a350731896086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Configurar certificados no servidor que executa o Microsoft Exchange Server Unified Messaging

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-26_

Se você tiver implantado UM (a) da Exchange Unified Messaging (UM), conforme descrito em [planejamento para a integração de Unificação de mensagens do Exchange no Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) na documentação de planejamento e desejar fornecer recursos de um do Exchange para usuários de Enterprise Voice em sua organização, você pode usar os procedimentos a seguir para configurar o certificado no servidor que executa o Exchange um.

<div>


> [!IMPORTANT]  
> Para certificados internos, os servidores que executam o Lync Server 2013 e os servidores que executam o Microsoft Exchange devem ter certificados de autoridade raiz confiáveis que sejam confiáveis mutuamente. A autoridade de certificação (CA) pode ser a mesma ou uma autoridade de certificação diferente, desde que os servidores tenham o certificado raiz da autoridade de certificação registrado no repositório de certificados da autoridade raiz confiável.



</div>

O servidor Exchange deve ser configurado com um certificado de servidor para se conectar ao Lync Server 2013:

1.  Baixe o certificado da CA para o servidor Exchange.

2.  Instale o certificado da CA para o servidor Exchange.

3.  Verifique se a CA está na lista de autoridades de certificação raiz confiáveis do servidor Exchange.

4.  Crie uma solicitação de certificado para o servidor Exchange e instale o certificado.

5.  Atribua o certificado para o servidor Exchange.

<div>

## <a name="to-download-the-ca-certificate"></a>Para baixar o certificado da CA

1.  No servidor que executa o Exchange UM, clique em **Iniciar**, clique em **executar**, digite **http://\<nome do seu servidor\>da CA de emissão/certsrv**e, em seguida, clique em **OK**.

2.  Em **Selecione uma tarefa**, clique em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**.

3.  Em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**, selecione **método de codificação para base 64**e, em seguida, clique em **baixar certificado da CA**.
    
    <div>
    

    > [!NOTE]  
    > Você também pode especificar a codificação de regras de codificação diferenciadas (DER) nesta etapa. Se você selecionar codificação DER, o tipo de arquivo na próxima etapa deste procedimento e na etapa 10 da <STRONG>para instalar o certificado da CA</STRONG> será. p7b em vez de. cer.

    
    </div>

4.  Na caixa de diálogo **download de arquivo** , clique em **salvar**e salve o arquivo no disco rígido no servidor. (O arquivo terá uma extensão de arquivo. cer ou. p7b, dependendo da codificação que você selecionou na etapa anterior.)

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>Para instalar o certificado da CA

1.  No servidor que executa o Exchange UM, abra o MMC (console de gerenciamento Microsoft) clicando em **Iniciar**, em **executar**, digitando **MMC** na caixa **abrir** e, em seguida, clicando em **OK**.

2.  No menu **arquivo** , clique em **Adicionar/remover snap-in**e, em seguida, clique em **Adicionar**.

3.  Na caixa **Adicionar Snap-ins Autônomos** , clique em **certificados**e, em seguida, clique em **Adicionar**.

4.  Na caixa de diálogo  **Snap-in de certificados**, clique em  **Conta de computador**e, em seguida, clique em  **Avançar**.

5.  Na caixa de diálogo **Selecionar computador** , verifique se a caixa de seleção **computador local: (o computador em que este console está sendo executado)** está marcada e clique em **concluir**.

6.  Clique em **fechar**e, em seguida, clique em **OK**.

7.  Na árvore de console, expanda **certificados (computador local)**, expanda **autoridades de certificação raiz confiáveis**e clique em **certificados**.

8.  Clique com o botão direito do mouse em **certificados**, clique em **todas as tarefas**e clique em **importar**.

9.  Click **Next**.

10. Clique em **procurar** para localizar o arquivo e, em seguida, clique em **Avançar**. (O arquivo terá uma extensão de arquivo. cer ou. p7b, dependendo da codificação selecionada na etapa 3 de **para baixar o certificado da autoridade de certificação**.

11. Clique em **colocar todos os certificados no repositório a seguir**.

12. Clique em **procurar**e, em seguida, selecione **autoridades de certificação raiz confiáveis**.

13. Clique em **Avançar** para verificar as configurações e, em seguida, clique em **concluir**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>Para verificar se a CA está na lista de autoridades de certificação raiz confiáveis

1.  No servidor que executa o Exchange UM, no MMC expanda **certificados (computador local)**, expanda **autoridades de certificação raiz confiáveis**e clique em **certificados**.

2.  No painel detalhes, verifique se a sua CA está na lista de CAs confiáveis.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Para configurar o Exchange Server 2013 UM com o Lync Server

1.  Para obter detalhes, consulte "integrar o Exchange 2013 UM com o Lync Server" na documentação do [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)Exchange Server em.

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Para criar uma solicitação de certificado e instalar o certificado no Exchange Server 2007 (SP1)

1.  No servidor que executa o Exchange um, clique em **Iniciar**, clique em **executar**, digite **\<http://** nome do seu servidor**\>** da CA de emissão/certsrv e, em seguida, clique em **OK**.

2.  Em **Selecione uma tarefa**, clique em **solicitar um certificado**.

3.  Em **solicitar um certificado**, clique em **solicitação avançada de certificado**.

4.  Em **solicitação avançada de certificado**, clique em **criar e envie uma solicitação para esta ca**.

5.  Em **solicitação de certificado avançada**, selecione **servidor Web** ou outro modelo de certificado de servidor configurado para autenticação do servidor.

6.  Em **informações de identificação para modelo offline**, na caixa **nome** , digite o nome de domínio totalmente qualificado (FQDN) do servidor Exchange.
    
    <div>
    

    > [!NOTE]  
    > Você deve digitar o FQDN do servidor Exchange para que as comunicações funcionem.

    
    </div>

7.  Em **Opções de chave**, clique na caixa de seleção **armazenar certificado no repositório de certificados do computador local** .

8.  Clique no botão **Enviar** na parte inferior da página da Web.

9.  Na caixa de diálogo que é exibida solicitando confirmação, clique em **Sim**.

10. Na página certificado emitido, em **certificado emitido**, clique em **instalar este certificado**.

11. Na caixa de diálogo que é exibida solicitando confirmação, clique em **Sim**.

12. Verifique se a mensagem "o novo certificado foi instalado com sucesso" é exibida.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Para criar um certificado no Exchange Server 2010

1.  Faça logon no servidor que está executando o Exchange UM com direitos de usuário adequados. Para obter detalhes, consulte "permissões de acesso do [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)cliente" em.

2.  Consulte os procedimentos a seguir para criar o certificado:
    
    1.  "Criar um novo certificado do Exchange" em[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Importar um certificado do Exchange" em[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Para o <STRONG>nome do requerente</STRONG>do certificado, você deve digitar o FQDN do servidor Exchange para que as comunicações funcionem.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Para atribuir o certificado no Exchange Server 2007 (SP1)

1.  No servidor que executa o Exchange UM, abra o MMC.

2.  Na árvore de console, expanda **pessoal** e, em seguida, clique em **certificados**.

3.  No painel detalhes, verifique se o certificado pessoal está exibido.

4.  Clique duas vezes no certificado para ler seus detalhes e verificar se ele é válido.
    
    <div>
    

    > [!NOTE]  
    > Pode demorar alguns minutos para que o certificado seja exibido como válido.

    
    </div>

5.  Reinicie o serviço de Unificação de mensagens do Microsoft Exchange.
    
    <div>
    

    > [!NOTE]  
    > O servidor que executa o Exchange Server 2007 SP1 Unified Messaging recupera automaticamente o certificado correto.

    
    </div>

6.  Abra o Visualizador de eventos e procure o ID de evento 1112, que especifica qual certificado o servidor que está executando o Exchange Server 2007 SP1 Unified Messaging foi recuperado.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Para atribuir o certificado no Exchange Server 2010

1.  Faça logon no servidor que está executando o Exchange UM com direitos de usuário adequados. Para obter detalhes, consulte "permissões de acesso do [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)cliente" em.

2.  Para obter o procedimento para atribuir o certificado, consulte "atribuir serviços a um certificado" [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

