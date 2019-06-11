---
title: 'Lync Server 2013: Configurar certificados para a interface de borda externa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cb33a91d6609f9109e6416f5688d1b2ddfb9ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a>Configurar certificados para a interface de borda externa para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Ao executar o assistente de certificado, certifique-se de que você esteja conectado usando uma conta que seja membro de um grupo que tenha recebido as permissões apropriadas para o tipo de modelo de certificado que você vai usar. Por padrão, uma solicitação de certificado do Lync Server vai usar o modelo de certificado de servidor Web. Se você usar uma conta que seja um membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando esse modelo, verifique se o grupo recebeu as permissões de Registro necessárias para usar esse modelo.



</div>

Cada servidor de borda requer um certificado público na interface entre a rede de perímetro e a Internet, e o nome alternativo do requerente do certificado deve conter os nomes externos do serviço de borda de acesso e o serviço de borda de webconferências totalmente FQDNs (nomes de domínio qualificados).

Para obter detalhes sobre esse e outros requisitos de certificado, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Para obter uma lista de autoridades de certificação (CAs) públicas que fornecem certificados compatíveis com requisitos específicos para certificados de comunicação unificada e associados à Microsoft para garantir que elas funcionem com o assistente de certificado do Lync Server 2013, consulte Artigo da base de dados de conhecimento Microsoft 929395, "parceiros de certificado de comunicação unificada para Exchange [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)Server e Communications Server" em.

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a>Configurar certificados nas interfaces externas

Para configurar um certificado na interface de borda externa em um site, use os procedimentos desta seção para fazer o seguinte:

  - Crie a solicitação de certificado para a interface externa do servidor de borda.

  - Envie a solicitação para sua CA pública.

  - Importar o certificado para a interface externa de cada servidor de borda.

  - Atribua o certificado para a interface externa de cada servidor de borda.

  - Se a sua implantação inclui vários servidores de borda, exporte o certificado juntamente com sua chave particular e copie-o para outros servidores de borda. Em seguida, para cada servidor de borda, importe-o e atribua-o conforme descrito anteriormente. Repita esse procedimento para cada servidor de borda.

Você pode solicitar certificados públicos diretamente de uma CA (autoridade de certificação) pública (por exemplo, do site de uma CA pública). Os procedimentos desta seção usam o assistente de certificado para a maioria das tarefas de certificado. Se você optou por solicitar um certificado diretamente de uma CA pública, será necessário modificar cada procedimento conforme apropriado para solicitar, transportar e importar o certificado e também para importar a cadeia de certificados.

Quando você solicita um certificado de uma autoridade de certificação externa, as credenciais fornecidas devem ter direitos de solicitar um certificado dessa CA. Cada CA tem uma política de segurança que define quais credenciais (ou seja, nomes de usuário e grupo específicos) têm permissão para solicitar, emitir, gerenciar ou ler certificados.

Se você decidir usar o console de gerenciamento da Microsoft (MMC) de certificados para importar a cadeia de certificados e o certificado, será necessário importá-los para o repositório de certificados do computador. Se você importá-los para o repositório de certificados do usuário ou do serviço, o certificado não estará disponível para atribuição no assistente de certificado do Lync Server 2013.

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a>Para criar a solicitação de certificado para a interface externa do servidor de borda

1.  No servidor de borda, no assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.
    
    <div>
    

    > [!NOTE]  
    > Se a sua organização quiser dar suporte à conectividade de mensagens instantâneas (IM) pública com a AOL, você não poderá usar o assistente de implantação do Lync Server para solicitar o certificado. Em vez disso, execute as etapas na etapa "para criar uma solicitação de certificado para a interface externa do servidor de borda para dar suporte à conectividade de IM pública com a AOL", mais adiante neste tópico.<BR>Se você tiver vários servidores de borda em um local em um pool, poderá executar o assistente de certificado do Lync Server 2013 em qualquer um dos servidores de borda.

    
    </div>

2.  Na página **Tarefas de Certificado Disponíveis**, clique em  **Criar uma nova solicitação de certificado**.

3.  Na página **solicitação de certificado** , clique em **certificado de borda externa**.

4.  Na página **solicitação atrasada ou imediata** , marque a caixa de seleção **preparar a solicitação agora, mas enviá-la mais tarde** .

5.  Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação deve ser salva (por exemplo, c:\\CERT\_guia\_Edge. cer).

6.  Na página **especificar modelo de certificado alternativo** , para usar um modelo diferente do modelo padrão do webserver, marque a caixa de seleção **usar modelo de certificado alternativo para a autoridade de certificação selecionada** .

7.  Na página **configurações de nome e segurança** , faça o seguinte:
    
      - Em **nome amigável**, digite um nome de exibição para o certificado.
    
      - Em **comprimento de bit**, especifique o comprimento do bit (geralmente, o padrão de **2048**).
    
      - Verifique se a caixa de seleção **Marcar chave privada de certificado como** exportável está marcada.

8.  Na página **informações da organização** , digite o nome da organização e da unidade organizacional (por exemplo, uma divisão ou um departamento).

9.  Na página **informações** geográficas, especifique as informações de localização.

10. Na página **nome do assunto/nomes alternativos de assunto** , as informações a serem automaticamente preenchidas pelo assistente serão exibidas. Se forem necessários nomes alternativos de entidades adicionais, especifique-os nas próximas duas etapas.

11. Na **configuração de domínio SIP na página de nomes alternativos de entidades (SANs)** , marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de assunto.

12. Na página **configurar nomes alternativos de entidades adicionais** , especifique os nomes alternativos de entidades adicionais necessários.

13. Na página **Resumo da solicitação** , examine as informações do certificado a serem usadas para gerar a solicitação.

14. Depois que os comandos terminarem de ser executados, faça o seguinte:
    
      - Para exibir o log para a solicitação de certificado, clique em **Exibir log**.
    
      - Para concluir a solicitação de certificado, clique em **Avançar**.

15. Na página **arquivo de solicitação de certificado** , faça o seguinte:
    
      - Para exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado, clique em **Exibir**.
    
      - Para fechar o assistente, clique em **Concluir**.

16. Copie o arquivo de saída para um local onde você possa enviá-lo para a CA pública.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Para criar uma solicitação de certificado para a interface externa do servidor de borda para dar suporte à conectividade de mensagem de chat pública com a AOL

1.  Quando o modelo obrigatório estiver disponível para a autoridade de certificação, use o seguinte cmdlet do Windows PowerShell no servidor de borda para solicitar o certificado:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    O nome de certificado padrão do modelo fornecido no Lync Server 2013 é o servidor Web. Especifique somente o \<nome\> do modelo se precisar usar um modelo diferente do modelo padrão.
    
    <div>
    

    > [!NOTE]  
    > Se a sua organização quiser dar suporte à conectividade de mensagem instantânea pública com a AOL, você deve usar o Windows PowerShell em vez do assistente de certificado para solicitar que o certificado seja atribuído à borda externa do serviço de borda de acesso. Isso ocorre porque o modelo de servidor Web do Lync Server 2013 que o assistente de certificado usa para solicitar um certificado não dá suporte à configuração de EKU de cliente. Antes de usar o Windows PowerShell para criar o certificado, o administrador da CA deve criar e implantar um novo modelo compatível com o EKU do cliente.

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a>Para enviar uma solicitação para uma autoridade de certificação pública

1.  Abra o arquivo de saída.

2.  Copie e cole o conteúdo da solicitação de assinatura de certificado (CSR).

3.  Se solicitado, especifique o seguinte:
    
      - A **Microsoft** como a plataforma do servidor.
    
      - **IIS** como a versão.
    
      - **Servidor Web** como o tipo de uso.
    
      - **PKCS7** como o formato de resposta.

4.  Quando a autoridade de certificação pública tiver verificado suas informações, você receberá uma mensagem de email com o texto necessário para o seu certificado.

5.  Copie o texto da mensagem de email e salve o conteúdo em um arquivo de texto (. txt) em seu computador local.

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a>Para importar o certificado para a interface externa do servidor de borda

1.  Faça logon como membro do grupo Administradores para o mesmo servidor de borda em que você criou a solicitação de certificado.

2.  No assistente de implantação, na página **implantar servidor de borda** , ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.

3.  Na página **tarefas de certificado disponíveis** , clique em **importar um certificado de um arquivo. p7b, pfx ou. cer**.

4.  Na página **importar certificado** , clique em **procurar** para localizar e selecionar o certificado que você solicitou para a interface externa do servidor de borda (ou, você pode digitar o caminho completo e o nome do arquivo). Se o certificado contiver uma chave privada, selecione **arquivo de certificado contém a chave privada do certificado** e digite a senha da chave privada. Click **Next**.

5.  Na página **importar Resumo do certificado** , examine o resumo e clique em **Avançar**.

6.  Na **execução de comandos**, examine os resultados da importação, clique em **Exibir log** para obter mais informações conforme necessário e clique em **concluir** para concluir a importação de certificado.

7.  Se você estiver configurando um pool do servidor de borda, exporte o certificado com sua chave privada, conforme descrito no procedimento "para exportar o certificado com a chave privada para servidores de borda em um pool" mais adiante neste tópico. Copie o arquivo de certificado exportado para os outros servidores de borda e importe-o para a loja do computador em cada servidor de borda.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Para exportar o certificado com a chave privada para servidores de borda em um pool

1.  Faça logon como membro do grupo Administradores para o mesmo servidor de borda no qual você importou o certificado.

2.  Clique em **Iniciar**, clique em **executar**e digite **MMC**.

3.  No console do console de gerenciamento Microsoft (MMC), clique em **arquivo**e, em seguida, clique em **Adicionar/remover snap-in**.

4.  Em **Adicionar ou remover snap-ins**, clique em **certificados**e, em seguida, clique em **Adicionar**.

5.  Na caixa de diálogo **certificados** , selecione **conta de computador**, clique em **Avançar**, selecione **computador local: (o computador em que este console está sendo executado)** em **Selecionar computador**, clique em **concluir** e em **OK** para configuração completa do console MMC.

6.  Clique duas vezes em **certificados (computador local)** para expandir os repositórios de certificados, clique duas vezes em **pessoal**e, em seguida, clique duas vezes em **certificados**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se não houver certificados no armazenamento pessoal de certificados do computador local, não há uma chave privada associada ao certificado que foi importado. Examine as etapas de solicitação e importação. Se o problema persistir, entre em contato com o administrador ou o provedor da autoridade de certificação.

    
    </div>

7.  No **repositório pessoal de certificados do computador local**, clique com o botão direito do mouse no certificado que você está exportando, clique em **todas as tarefas**e, em seguida, clique em **Exportar**.

8.  No Assistente para exportação de certificados, clique em **Avançar**, selecione **Sim, exportar a chave particular**e, em seguida, clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Se a seleção <STRONG>Sim, exportar a chave privada</STRONG> não estiver disponível, a chave privada associada a esse certificado não foi marcada para exportação. Você precisará solicitar o certificado novamente, certificando-se de que o certificado esteja marcado para permitir a exportação da chave privada antes de continuar com a exportação. Entre em contato com o administrador ou provedor da autoridade de certificação.

    
    </div>

9.  Na caixa de diálogo Exportar formatos de arquivo, selecione **troca de informações\#pessoais – PKCS 12 (. PFX)** e, em seguida, selecione o seguinte:
    
      - Incluir todos os certificados no caminho de certificação, se possível
    
      - Exportar todas as propriedades estendidas
        
        <div>
        

        > [!WARNING]  
        > Ao exportar o certificado de um servidor de borda, não selecione <STRONG>excluir a chave privada se a exportação for bem-sucedida</STRONG>. Selecionar essa opção exigirá que você importe o certificado e a chave privada para esse servidor de borda.

        
        </div>

10. Click **Next**.

11. Digite uma senha para a chave privada, digite a senha novamente para confirmá-la e clique em **Avançar**.

12. Digite um caminho e o nome de arquivo para o certificado exportado, usando uma extensão de arquivo .pfx. O caminho deve ser acessível a todos os outros servidores de borda do pool ou disponível para transporte por meio de mídia removível-por exemplo, uma unidade flash USB. Click **Next**.

13. Examine o resumo em **concluindo o assistente para exportação de certificados**e clique em **concluir**.

14. Na caixa de diálogo exportação bem-sucedida, clique em **OK**.

15. Importe o arquivo de certificado exportado para os outros servidores de borda seguindo as etapas descritas no procedimento "para importar o certificado para a interface externa do servidor de borda" anteriormente neste tópico.

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a>Para atribuir o certificado para a interface externa do servidor de borda

1.  Em cada servidor de borda, no assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.

2.  Na página **tarefas de certificado disponíveis** , clique em **atribuir um certificado existente**.

3.  Na página **atribuição de certificado** , clique em **certificado de borda externa** e marque a caixa de seleção **usos avançados de certificado** .

4.  Na página **usos avançados de certificado** , marque todas as caixas de seleção para atribuir o certificado para todos os usos.

5.  Na página **repositório de certificados** , selecione o certificado público que você solicitou e importou para a interface externa do servidor de borda.
    
    <div>
    

    > [!NOTE]  
    > Se o certificado que você solicitou e importado não estiver na lista, um dos métodos de solução de problemas será verificar se o nome da entidade e os nomes alternativos da entidade do certificado atendem a todos os requisitos do certificado e, se você importou manualmente o certificado e cadeia de certificados em vez de usar os procedimentos anteriores, que o certificado está no repositório de certificados correto (o repositório de certificados do computador, não o usuário ou o repositório de certificados do serviço).

    
    </div>

6.  Na página **Resumo de atribuição de certificado** , examine suas configurações e clique em **Avançar** para atribuir os certificados.

7.  Na página de conclusão do assistente, clique em  **Concluir**.

8.  Depois de usar esse procedimento para atribuir o certificado de borda, abra o snap-in de certificado em cada servidor, expanda **certificados (computador local)**, expanda **pessoal**, clique em **certificados**e verifique o painel de detalhes que o certificado está listado.

9.  Se a sua implantação incluir vários servidores de borda, repita esse procedimento para cada servidor de borda.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

