---
title: 'Lync Server 2013: Configurar certificados para a interface de borda interna'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6e462bdc629308493799c857ecb6b2434dc268
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Configurar certificados para a interface de borda interna no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

<div>


> [!IMPORTANT]  
> Ao executar o assistente de certificado, certifique-se de que você esteja conectado usando uma conta que seja membro de um grupo que tenha recebido as permissões apropriadas para o tipo de modelo de certificado que você vai usar. Por padrão, uma solicitação de certificado do Lync Server 2013 usará o modelo de certificado de servidor Web. Se você usar uma conta que seja um membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando esse modelo, verifique se o grupo recebeu as permissões de Registro necessárias para usar esse modelo.



</div>

É necessário um único certificado na interface interna de cada servidor de borda. Certificados para a interface interna podem ser emitidos por uma CA (autoridade de certificação) corporativa interna ou uma CA pública. Se a sua organização tiver uma CA interna implantada, você poderá economizar na despesa de usar certificados públicos usando a CA interna para emitir o certificado para a interface interna. Você pode usar uma CA interna do Windows Server 2008 ou uma autoridade de certificação do Windows Server 2008 R2 para criar esses certificados.

Para obter detalhes sobre esse e outros requisitos de certificado, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Para configurar certificados na interface de borda interna em um site, use os procedimentos desta seção para fazer o seguinte:

1.  Baixe a cadeia de certificação da CA para a interface interna para cada servidor de borda.

2.  Importar a cadeia de certificação da CA para a interface interna, em cada servidor de borda.

3.  Crie a solicitação de certificado para a interface interna, em um servidor de borda, chamado de primeiro servidor de borda.

4.  Importar o certificado para a interface interna no primeiro servidor de borda.

5.  Importar o certificado nos outros servidores de borda neste site (ou implantado atrás deste balanceador de carga).

6.  Atribua o certificado para a interface interna de cada servidor de borda.

Se você tiver mais de um site com servidores de borda (ou seja, uma topologia de borda de vários sites) ou conjuntos separados de servidores de Borda implantados por meio de balanceadores de carga diferentes, você precisará seguir estas etapas para cada site que tenha servidores de borda e para cada conjunto de servidores de borda implantado atrás de um balanceador de carga diferente.

<div>


> [!NOTE]  
> As etapas para procedimentos nesta seção se baseiam no uso de uma autoridade&nbsp;de certificação do windows Server&nbsp;2008&nbsp;, do Windows Server 2008 R2, da autoridade de certificação do Windows Server 2012 ou da autoridade de certificação do Windows Server 2012 R2 para criar um certificado para cada servidor de borda. Para obter orientação passo a passo para qualquer outra autoridade de certificação, consulte a documentação dessa CA. Por padrão, todos os usuários autenticados têm os direitos de usuário adequados para solicitar certificados.<BR>Os procedimentos desta seção se baseiam na criação de solicitações de certificado no servidor de borda como parte do processo de implantação do servidor de borda. É possível criar solicitações de certificado usando o servidor front-end. Você pode fazer isso para concluir a solicitação de certificado no início do processo de planejamento e implantação antes de iniciar a implantação dos servidores de borda. Para fazer isso, você deve certificar-se de que o certificado que você solicitou está definido com uma chave privada exportável.<BR>Os procedimentos desta seção descrevem o uso de um arquivo. cer e de um arquivo. p7b para o certificado. Se você usar um tipo de arquivo diferente, modifique esses procedimentos conforme apropriado.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>Para baixar a cadeia de certificação CA para a interface interna usando o site do certsrv

1.  Faça logon em um servidor do Lync Server 2013 na rede interna (ou seja, não no servidor de borda) como membro do grupo **Administradores** .

2.  Execute o seguinte comando em um prompt de comando clicando em **Iniciar**, em **executar**e, em seguida, digitando o seguinte:
    
        https://<name of your Issuing CA Server>/certsrv
    
    Por exemplo:
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Se estiver usando uma autoridade de certificação empresarial do Windows Server 2008 ou do Windows Server 2008 R2, você deve usar HTTPS, não http.

    
    </div>

3.  Na página web certsrv da AC emissora, em  **Selecione uma tarefa**, clique em **Download de um Certificado de Autoridade de Certificação, Cadeia de Certificados ou Lista de Certificados Revogados**.

4.  Em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**, clique em **baixar cadeia de certificados da CA**.

5.  Na caixa de diálogo **download de arquivo** , clique em **salvar**.

6.  Salve o arquivo. p7b na unidade de disco rígido no servidor e copie-o para uma pasta em cada servidor de borda.
    
    <div>
    

    > [!NOTE]  
    > O arquivo. p7b contém todos os certificados que estão no caminho de certificação. Para exibir o caminho de certificação, abra o certificado do servidor e clique no caminho de certificação.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>Para exportar a cadeia de certificação da CA para a interface interna usando o MMC

1.  Você pode exportar o certificado raiz da autoridade de certificação de qualquer computador ingressado no domínio usando o console de gerenciamento Microsoft (MMC). Clique em **Iniciar**, clique em **executar**e digite **MMC**.

2.  No console MMC, clique em **arquivo**, clique em **Adicionar/remover**.

3.  Na lista de diálogo **Adicionar ou remover snap-ins** , selecione **certificados**e clique em **Adicionar**. Quando solicitado, selecione **conta do computador**. Na caixa de diálogo **Selecionar Computador**, selecione **Computador Local**. Clique em **Concluir**. Clique em **OK**.

4.  Expanda **Certificates (computador local)**. Expanda **autoridades de certificação raiz confiáveis**, selecione **certificados**.

5.  Clique no certificado raiz emitido por sua AC. Clique com o botão direito do mouse no certificado, selecione **todas as tarefas**, selecione **Exportar**. O **Assistente para exportação de certificados** será aberto.

6.  No **Assistente de Exportação de Certificado**, clique em  **Avançar**.

7.  Na caixa de diálogo **exportar formato de arquivo** , selecione um formato para o qual exportar. Recomendamos o **padrão de sintaxe da mensagem criptográfica \#– Certificados PKCS 7 (. P7B)**. Se você selecionar o **padrão de sintaxe da mensagem criptográfica \#– Certificados PKCS 7 (. P7B)**, marque a caixa de seleção **incluir todos os certificados no caminho de certificação, se possível** , para exportar a cadeia de certificados, incluindo o certificado da CA raiz e qualquer certificado de autoridade de certificação intermediário. Click **Next**.

8.  Na caixa de diálogo **arquivo para exportação** na entrada nome do arquivo, digite um nome de caminho e arquivo (extensão padrão é. p7b) para o certificado exportado. Opcionalmente, clique em **procurar**, localize um diretório para colocar o certificado exportado e forneça um nome para o certificado exportado. Clique em **Salvar**. Click **Next**.

9.  Examine o resumo de ações e clique em **concluir** para concluir a exportação do certificado. Clique em **OK** para confirmar que a exportação foi bem sucedida.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>Para importar a cadeia de certificação da CA para a interface interna

1.  Em cada servidor de borda, abra o MMC (console de gerenciamento Microsoft) clicando em **Iniciar**, clicando em **executar**, digitando **MMC** na caixa **abrir** e, em seguida, clicando em **OK**.

2.  No menu **arquivo** , clique em **Adicionar/remover snap-in**e, em seguida, clique em **Adicionar**.

3.  Na caixa **Adicionar Snap-ins Autônomos** , clique em **certificados**e, em seguida, clique em **Adicionar**.

4.  Na caixa de diálogo  **Snap-in de certificados**, clique em  **Conta de computador**e, em seguida, clique em  **Avançar**.

5.  Na caixa de diálogo **Selecionar computador** , verifique se a caixa de seleção **computador local: (o computador em que este console está sendo executado)** está marcada e clique em **concluir**.

6.  Clique em **fechar**e, em seguida, clique em **OK**.

7.  Na árvore de console, expanda **certificados (computador local)**, clique com o botão direito do mouse em **autoridades de certificação raiz confiáveis**, aponte para **todas as tarefas**e, em seguida, clique em **importar**.

8.  No assistente, em **arquivo a ser importado**, especifique o nome do arquivo do certificado (ou seja, o nome que você especificou quando baixou a cadeia de certificação CA para a interface interna no procedimento anterior).

9.  Repita esse procedimento em cada servidor de borda.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>Para criar a solicitação de certificado para a interface interna

1.  Em um dos servidores de borda, inicie o assistente de implantação e, em seguida, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique em **executar**.
    
    <div>
    

    > [!NOTE]  
    > Se você tiver vários servidores de borda em um local em um pool, poderá executar o assistente de certificado em qualquer um dos servidores de borda.<BR>Depois de executar a etapa 3 na primeira vez, o botão muda para <STRONG>executar novamente</STRONG>, e uma marca de seleção verde que indica que a conclusão bem-sucedida da tarefa não é exibida até que todos os certificados exijam a solicitação, instalação e atribuição.

    
    </div>

2.  Na página **Tarefas de Certificado Disponíveis**, clique em  **Criar uma nova solicitação de certificado**.

3.  Na página **solicitação de certificado** , clique em **Avançar**.

4.  Na página  **Solicitações Atrasadas ou Imediatas**, clique em  **Preparar a solicitação agora, mas enviá-la depois**.

5.  Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação deve ser salva (por exemplo, **c\_:\\borda interna do CERT\_. cer**).

6.  Na página **especificar modelo de certificado alternativo** , para usar um modelo diferente do modelo padrão do webserver, marque a caixa de seleção **usar modelo de certificado alternativo para a autoridade de certificação selecionada** .

7.  Na página **configurações de nome e segurança** , faça o seguinte:
    
      - Em **nome amigável**, digite um nome de exibição para o certificado (por exemplo, borda interna).
    
      - Em **comprimento de bit**, especifique o comprimento do bit (geralmente, o padrão de **2048**).
        
        <div>
        

        > [!NOTE]  
        > Comprimentos de bit mais altos oferecem mais segurança, mas têm um impacto negativo na velocidade.

        
        </div>
    
      - Se o certificado precisar ser exportável, marque a caixa de seleção **Marcar chave privada de certificado como exportável** .

8.  Na página **informações da organização** , digite o nome da organização e a unidade organizacional (ou) (por exemplo, uma divisão ou um departamento).

9.  Na página **informações geográficas** , especifique as informações de localização.

10. Na página **nome do assunto/nomes alternativos de assunto** , as informações a serem automaticamente preenchidas pelo assistente serão exibidas.

11. Na página **configurar nomes alternativos de entidades adicionais** , especifique os nomes alternativos de entidades adicionais necessários.

12. Na página **Resumo da solicitação** , examine as informações do certificado que serão usadas para gerar a solicitação.

13. Depois que os comandos forem concluídos, faça o seguinte:
    
      - Para exibir o log para a solicitação de certificado, clique em **Exibir log**.
    
      - Para concluir a solicitação de certificado, clique em **Avançar**.

14. Na página **arquivo de solicitação de certificado** , faça o seguinte:
    
      - Para exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado, clique em **Exibir**.
    
      - Para fechar o assistente, clique em **Concluir**.

15. Envie este arquivo para a sua CA (por email ou outro método compatível com sua organização para a sua CA corporativa) e, quando você receber o arquivo de resposta, copie o novo certificado para este computador para que ele esteja disponível para importação.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>Para importar o certificado para a interface interna

1.  Faça logon no servidor de borda em que você criou a solicitação de certificado como membro do grupo Administradores local.

2.  No assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.
    
    Depois de executar a etapa 3 na primeira vez, o botão muda para **executar novamente**, mas uma marca de seleção verde (indicando a conclusão bem-sucedida da tarefa) não é exibida até que todos os certificados exijam que os certificados tenham sido solicitados, instalados e atribuídos.

3.  Na página **tarefas de certificado disponíveis** , clique em **importar um certificado de a. Arquivo P7b,. pfx ou. cer**.

4.  Na página **importar certificado** , digite o caminho completo e o nome do arquivo do certificado que você solicitou e recebeu para a interface interna deste servidor de borda (ou clique em **procurar** para localizar e selecionar o arquivo).

5.  Se você estiver importando certificados para outros membros do pool um certificado contendo uma chave privada, marque a caixa de seleção o **arquivo de certificado contém a chave privada da Certifcate** e especifique a senha.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Para exportar o certificado com a chave privada para servidores de borda em um pool

1.  Faça logon como membro do grupo Administradores para o mesmo servidor de borda no qual você importou o certificado.

2.  Clique em **Iniciar**, clique em **executar**e digite **MMC**.

3.  No console do MMC, clique em **arquivo**, clique em **Adicionar/remover snap-in**.

4.  Na página Adicionar ou remover snap-ins, clique em **certificados**e, em seguida, clique em **Adicionar**.

5.  Na caixa de diálogo snap-in de certificados, selecione **conta de computador**. Click **Next**. Em Selecionar computador, selecione **computador local: (o computador no qual este console está sendo executado)**. Clique em **Concluir**. Clique em **OK** para concluir a configuração do console MMC.

6.  Clique duas vezes em **Certificados (Computador Local)** para expandir os repositórios de certificados. Clique duas vezes em **pessoal**e, em seguida, clique duas vezes em **certificados**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se não houver certificados no armazenamento pessoal de certificados do computador local, não há uma chave privada associada ao certificado que foi importado. Examine as etapas de solicitação e importação. Se o problema persistir, entre em contato com o administrador ou o provedor da autoridade de certificação.

    
    </div>

7.  No armazenamento de certificados pessoal do computador local, clique com o botão direito do mouse no certificado que você está exportando. Clique em **todas as tarefas**, clique em **Exportar**.

8.  No Assistente para exportação de certificados, clique em **Avançar**. Selecione **Sim, exportar a chave privada**. Clique em **Avançar**.
    
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
    
    Clique em **Avançar** para continuar.

10. Se você quiser atribuir uma senha para proteger a chave privada, digite uma senha para a chave privada. Digite a senha novamente para confirmá-la. Click **Next**.

11. Digite um caminho e o nome de arquivo para o certificado exportado, usando uma extensão de arquivo .pfx. O caminho deve ser acessível a todos os outros servidores de borda do pool ou disponível para transporte por meio de mídia removível-por exemplo, uma unidade flash USB. Click **Next**.

12. Examine o resumo na caixa de diálogo concluindo o assistente para exportação de certificados. Clique em **Concluir**.

13. Clique em **OK** na caixa de diálogo da exportação com sucesso.

14. Importe o arquivo de certificado exportado para os outros servidores de borda seguindo as etapas descritas nos procedimentos [configurar certificados para a interface de borda externa dos procedimentos do Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>Para atribuir o certificado interno nos servidores de borda

1.  Em cada servidor de borda, no assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.

2.  Na página **tarefas de certificado disponíveis** , clique em **atribuir um certificado existente**.

3.  Na página **Atribuição de Certificado**, selecione  **Interno à Borda** na lista.

4.  Na página **repositório de certificados** , selecione o certificado que você importou para a borda interna (do procedimento anterior).

5.  Na página **Resumo de atribuição de certificado** , examine suas configurações e clique em **Avançar** para atribuir os certificados.

6.  Na página de conclusão do assistente, clique em  **Concluir**.

7.  Depois de usar esse procedimento para atribuir o certificado de borda interno, abra o snap-in de certificado em cada servidor, expanda **certificados (computador local)**, expanda **pessoal**, clique em **certificados**e verifique no painel de detalhes se o certificado de borda interna está listado.

8.  Se a sua implantação incluir vários servidores de borda, repita esse procedimento para cada servidor de borda.

</div>

</div>

<span> </span>

</div>

</div>

</div>

