---
title: 'Lync Server 2013: configurar certificados no servidor que executa a Unificação de mensagens do Microsoft Exchange Server'
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
ms.openlocfilehash: 4bf3e665e0031596bc2db2273882aef379a96f2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Configurar certificados no servidor que executa a Unificação de mensagens do Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-26_

Se você implantou a Unificação de mensagens (UM) do Exchange, conforme descrito em [Planning for Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) na documentação de planejamento e deseja fornecer recursos da um do Exchange para usuários do Enterprise Voice em sua organização, você pode usar os seguintes procedimentos para configurar o certificado no servidor que executa o Exchange um.

<div>


> [!IMPORTANT]  
> Para certificados internos, ambos os servidores que executam o Lync Server 2013 e os servidores que executam o Microsoft Exchange devem ter certificados de autoridade raiz confiáveis mutuamente confiáveis. A autoridade de certificação (CA) pode ser a mesma ou uma autoridade de certificação diferente, desde que os servidores tenham o certificado raiz da autoridade de certificação registrado no repositório de certificados da autoridade raiz confiável.



</div>

O servidor do Exchange deve ser configurado com um certificado de servidor para se conectar ao Lync Server 2013:

1.  Baixe o certificado da autoridade de certificação do Exchange Server.

2.  Instale o certificado da autoridade de certificação do Exchange Server.

3.  Verifique se a autoridade de certificação está na lista de autoridades de certificação raiz confiáveis do Exchange Server.

4.  Crie uma solicitação de certificado do Exchange Server e instale o certificado.

5.  Atribua o certificado do Exchange Server.

<div>

## <a name="to-download-the-ca-certificate"></a>Para baixar o certificação da autoridade de certificação

1.  No servidor que executa o UM do Exchange, clique em **Iniciar**, clique em **executar**, digite **http://\<nome do servidor\>de CA de emissão/certsrv**e clique em **OK**.

2.  Em **Selecionar uma tarefa**, clique em **Download de um certificado de autoridade de certificação, cadeia de certificados ou lista de certificados revogados**.

3.  Em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**, selecione o **método de codificação como base 64**e clique em **baixar certificado de autoridade de certificação**.
    
    <div>
    

    > [!NOTE]  
    > Você também pode especificar a codificação de regras de codificação diferenciadas (DER) nesta etapa. Se você selecionar a codificação DER, o tipo de arquivo na próxima etapa deste procedimento e na etapa 10 de <STRONG>Para instalar o Certificado de autoridade de certificação</STRONG> é. p7b, em vez de .cer.

    
    </div>

4.  Na caixa de diálogo **Download de Arquivo**, clique em **Salvar** e salve o arquivo no disco rígido no servidor. (O arquivo terá um .cer ou uma extensão de arquivo .p7b, dependendo da codificação que você selecionou na etapa anterior).

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>Para instalar o certificado da autoridade de certificação

1.  No servidor que executa o UM do Exchange, abra o console de gerenciamento Microsoft (MMC) clicando em **Iniciar**, clicando em **executar**, digitando **MMC** na caixa **abrir** e clicando em **OK**.

2.  No menu **Arquivo**, clique em **Adicionar/Remover Snap-in** e em **Adicionar**.

3.  Na caixa **Adicionar Snap-in Autônomo**, clique em **Certificados** e em **Adicionar**.

4.  Na caixa de diálogo **Snap-in de certificados**, clique em **Conta de computador** e em **Avançar**.

5.  Na caixa de diálogo **Selecionar computador** , verifique se a caixa de seleção **computador local: (o computador em que este console está sendo executado)** está marcada e clique em **concluir**.

6.  Clique em **Fechar** e em **OK**.

7.  Na árvore de console, expanda **Certificados (Computador Local)**, expanda **Autoridades de Certificação Raiz Confiáveis** e clique em **Certificados**.

8.  Clique com o botão direito do mouse em **Certificados**, clique em **Todas as Tarefas** e em **Importar**.

9.  Clique em **Avançar**.

10. Clique em **Procurar** para localizar o arquivo e clique em **Avançar**. (O arquivo terá uma extensão de arquivo .cer ou .p7b, dependendo da codificação que você selecionou na etapa 3 de **Para baixar o certificado de autoridade de certificação**.

11. Clique em **Colocar todos os certificados no repositório a seguir**.

12. Clique em **Procurar** e selecione **Autoridades de Certificação Raiz Confiáveis**.

13. Clique em **Avançar** para verificar as configurações e, em seguida, clique em **Concluir**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>Para verificar se a autoridade de certificação está na lista de autoridades de certificação raiz confiáveis

1.  No servidor que executa o UM do Exchange, no MMC expanda **certificados (computador local)**, expanda **autoridades de certificação raiz confiáveis**e clique em **certificados**.

2.  No painel de detalhes, verifique se a autoridade de certificação está na lista de autoridades de certificação confiáveis.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Para configurar a UM do Exchange Server 2013 com o Lync Server

1.  Para obter detalhes, consulte "integrar o Exchange 2013 UM com Lync Server" na documentação do Exchange [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)Server em.

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Para criar uma solicitação de certificado e instalar o certificado no Exchange Server 2007 (SP1)

1.  No servidor que executa o um do Exchange, clique em **Iniciar**, clique em **executar**, digite **\<http://** nome do servidor**\>** de CA de emissão/certsrv e clique em **OK**.

2.  Em **Selecionar uma tarefa**, clique em **Solicitar um Certificado**.

3.  Em **Solicitar um Certificado**, clique em **Solicitação avançada de certificado**.

4.  Em **Solicitação Avançada de Certificado**, clique em **Criar e enviar uma solicitação para a autoridade de certificação**.

5.  Em **Solicitação Avançada de Certificado**, selecione **Servidor Web** ou outro modelo de certificado de servidor configurado para autenticação de servidor.

6.  Em **informações de identificação para modelo offline**, na caixa **nome** , digite o nome de domínio totalmente qualificado (FQDN) do servidor Exchange.
    
    <div>
    

    > [!NOTE]  
    > Você deve inserir o FQDN do Exchange Server para que a comunicação funcione.

    
    </div>

7.  Em **Opções de Chave**, clique na caixa de seleção **Armazenar certificado no armazenamento de certificados do computador local**.

8.  Clique no botão **Enviar** na parte inferior da página da Web.

9.  Na caixa de diálogo que solicita a confirmação, clique em **Sim**.

10. Na página Certificado Emitido, em **Certificado Emitido**, clique em **Instalar este certificado**.

11. Na caixa de diálogo que solicita a confirmação, clique em **Sim**.

12. Verifique se a mensagem "O novo certificado foi instalado com êxito" é exibida.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Para criar um certificado no Exchange Server 2010

1.  Faça logon no servidor que está executando o UM do Exchange com os direitos de usuário apropriados. Para obter detalhes, consulte "permissões de acesso do [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)cliente" em.

2.  Consulte os seguintes procedimentos para criar o certificado:
    
    1.  "Criar um novo certificado do Exchange" em[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Importar um certificado do Exchange" em[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Para o certificado <STRONG>Nome da Entidade</STRONG>, digite o FQDN do Exchange Server para que as comunicações funcionem.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Para atribuir o certificado no Exchange Server 2007 (SP1)

1.  No servidor que executa o Exchange UM, abra o MMC.

2.  Na árvore de console, expanda **Pessoal** e clique em **Certificados**.

3.  No painel de detalhes, verifique se o certificado pessoal é exibido.

4.  Clique duas vezes no certificado para ler seus detalhes e verificar se ele é válido.
    
    <div>
    

    > [!NOTE]  
    > Possivelmente levará alguns minutos para que o certificado apareça como válido.

    
    </div>

5.  Reinicie o serviço de Unificação de Mensagens do Microsoft Exchange.
    
    <div>
    

    > [!NOTE]  
    > O servidor que está executando a Unificação de Mensagens do Exchange Server 2007 SP1 recupera automaticamente o certificado correto.

    
    </div>

6.  Abra o Visualizador de Eventos e procure a ID de Evento 1112, que especifica qual certificado foi recuperado pelo servidor que está executando a Unificação de Mensagens do Exchange Server 2007 SP1.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Para atribuir o certificado no Exchange Server 2010

1.  Faça logon no servidor que está executando o UM do Exchange com os direitos de usuário apropriados. Para obter detalhes, consulte "permissões de acesso do [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)cliente" em.

2.  Para obter o procedimento para atribuir o certificado, consulte "atribuir serviços a um certificado" [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

