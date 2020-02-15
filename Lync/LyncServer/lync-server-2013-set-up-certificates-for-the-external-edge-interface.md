---
title: 'Lync Server 2013: configurar certificados para a interface de borda externa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d8e408425ccc2810072373212f48c764974dc0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a>Configurar certificados para a interface de borda externa para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Ao executar o Assistente de certificado, certifique-se de que esteja conectado usando uma conta membro de um grupo com as permissões apropriadas para o tipo de modelo de certificado que será usado. Por padrão, uma solicitação de certificado do Lync Server usará o modelo de certificado do servidor Web. Se você usar uma conta membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando este modelo, verifique se o grupo foi atribuído com permissões de Inscrição necessárias para usar este modelo.



</div>

Cada Servidor de Borda requer um certificado público na interface entre a rede de perímetro e a Internet, e o nome alternativo da entidade do certificado deve conter nomes externos do serviço de Borda de Acesso e FQDNs (nomes de domínio totalmente qualificado) do serviço de Borda de Webconferência.

Para obter detalhes sobre esse e outros requisitos de certificado, consulte [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Para obter uma lista de CAs (autoridades de certificação) públicas que fornecem certificados compatíveis com requisitos específicos para certificados de comunicações unificadas e que têm a parceria com a Microsoft para garantir que eles funcionem com o assistente de certificado do Lync Server 2013, consulte o artigo 929395 da base de dados de conhecimento da Microsoft, [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)"em.

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a>Configurando certificados nas interfaces externas

Para configurar um certificado na interface de borda externa em um site, use os procedimentos desta seção para fazer o seguinte:

  - Crie a solicitação de certificado para a interface externa do Servidor de Borda.

  - Envie a solicitação à autoridade de certificação pública.

  - Importe o certificado da interface externa de cada Servidor de Borda.

  - Atribua o certificado à interface externa de cada Servidor de Borda.

  - Se sua implantação incluir vários Servidores de Borda, exporte o certificado junto com sua chave privada e o copie para os Servidores de Borda. Em seguida, para cada Servidor de Borda, importe-o e atribua-o conforme descrito anteriormente. Repita este procedimento para cada Servidor de Borda.

Você pode solicitar os certificados públicos diretamente de uma autoridade de certificação pública (como a partir do site de uma autoridade de certificação pública). Os procedimentos nesta seção usam o Assistente de Certificados na maioria das tarefas do certificado. Se você optar por solicitar um certificado diretamente a partir de uma autoridade de certificação pública, precisará modificar cada procedimento conforme apropriado para solicitar, transportar e importar o certificado e também para importar a cadeia de certificados.

Quando você solicita um certificado junto a uma autoridade de certificação externa, as credenciais fornecidas devem ter direitos para solicitar um certificado nessa autoridade de certificação. Cada autoridade de certificação tem uma política de segurança que define quais credenciais (ou seja, nomes de usuário e grupo específicos) têm permissão para solicitar, emitir, gerenciar ou ler certificados.

Se você decidir usar MMC (Console de Gerenciamento Microsoft) de Certificados para importar a cadeia de certificados e o certificado, deverá importá-los para o repositório de certificados do computador. Se você importá-los para o repositório de certificados do usuário ou serviço, o certificado não estará disponível para atribuição no assistente de certificado do Lync Server 2013.

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a>Para criar a solicitação de certificado para a interface externa do Servidor de Borda

1.  No Servidor de Borda, no Assistente de Implantação, próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.
    
    <div>
    

    > [!NOTE]  
    > Se sua organização desejar oferecer suporte à conectividade pública de mensagens instantâneas com o AOL, você não pode usar o Assistente de Implantação do Lync Server para solicitar o certificado. Em vez disso, execute as etapas no procedimento "Para criar uma solicitação de certificado para a interface externa do Servidor de Borda para oferecer suporte à conectividade pública de IM com o AOL" posteriormente neste tópico.<BR>Se houver vários servidores de borda em um único local em um pool, você poderá executar o assistente de certificado do Lync Server 2013 em qualquer um dos servidores de borda.

    
    </div>

2.  Na página **Tarefas de Certificado Disponíveis**, clique em **Criar uma nova solicitação de certificado**.

3.  Na página **Solicitação de Certificado**, clique em **Certificado de Borda Externa**.

4.  Na página **Solicitação Atrasada ou Imediata**, marque a caixa de seleção **Preparar a solicitação agora, mas enviá-la depois**.

5.  Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação será salva (por exemplo, c:\\CERT\_externos\_Edge. cer).

6.  Na página **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo WebServer padrão, marque a caixa de seleção **Usar o modelo de certificado alternativo para a autoridade de certificação selecionada**.

7.  Na página **Nome e Configurações de Segurança**, siga estes procedimentos:
    
      - Em **Nome amigável**, digite um nome para exibição do certificado.
    
      - Em **Comprimento de bit**, especifique o comprimento de bit (geralmente, o padrão de **2048**).
    
      - Verifique se a caixa de seleção **Marcar chave privada de certificado como exportável**  está marcada.

8.  Na página **Informações da Organização**, digite o nome da organização e a unidade organizacional (por exemplo, uma divisão ou departamento).

9.  Na página **Informações Geográficas**, especifique as informações de localização.

10. Na página **Nome da Entidade/Nomes Alternativos da Entidade**, as informações a serem preenchidas automaticamente pelo assistente são exibidas. Se nomes alternativos de entidade adicionais forem necessários, especifique-os nas próximas duas etapas.

11. Na página **configuração do domínio SIP em nomes alternativos da entidade (SANs)** , marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de entidade.

12. Na página **Configurar Nomes Alternativos da Entidade Adicionais**, especifique qualquer nome alternativo adicional da entidade necessário.

13. Na página **Resumo da Solicitação**, examine as informações do certificado a ser usado para gerar a solicitação.

14. Após o término da execução de comandos, faça o seguinte:
    
      - Para exibir o log para a solicitação de certificado, clique em **Exibir Log**.
    
      - Para concluir a solicitação de certificado, clique em **Avançar**.

15. Na página **Arquivo de Solicitação de Certificado**, execute os seguintes procedimentos:
    
      - Para exibir um arquivo CSR (solicitação de assinatura de certificado) gerado, clique em **Exibir**.
    
      - Para fechar o assistente, clique em **Concluir**.

16. Copie o arquivo de saída para um local de onde você possa enviá-lo à autoridade de certificação pública.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Para criar uma solicitação de certificado para a interface externa do Servidor de Borda para oferecer suporte à conectividade pública de IM com o AOL

1.  Quando o modelo necessário estiver disponível para a autoridade de certificação, use o seguinte cmdlet do Windows PowerShell no servidor de borda para solicitar o certificado:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    O nome de certificado padrão do modelo fornecido no Lync Server 2013 é o servidor Web. Só especifique o \<nome\> do modelo se você precisar usar um modelo diferente do modelo padrão.
    
    <div>
    

    > [!NOTE]  
    > Se sua organização quiser suportar a conectividade pública de IM com o AOL, você deve usar o Windows PowerShell em vez do assistente de certificado para solicitar que o certificado seja atribuído à borda externa do serviço de borda de acesso. Isso ocorre porque o modelo de servidor Web do Lync Server 2013 que o assistente de certificado usa para solicitar um certificado não dá suporte à configuração de EKU do cliente. Antes de usar o Windows PowerShell para criar o certificado, o administrador da autoridade de certificação deve criar e implantar um novo modelo que dê suporte ao EKU do cliente.

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a>Para enviar uma solicitação a uma autoridade de certificação pública

1.  Abra o arquivo de saída.

2.  Copie e cole o conteúdo da CSR (Solicitação de Assinatura de Certificado).

3.  Se solicitado, especifique o seguinte:
    
      - **Microsoft** como plataforma de servidor.
    
      - **IIS** como versão.
    
      - **Servidor Web** como o tipo de uso.
    
      - **PKCS7** como o formato de resposta.

4.  Quando a autoridade de certificação pública tiver confirmado suas informações, você receberá uma mensagem de email contendo o texto necessário para o seu certificado.

5.  Copie o texto da mensagem de email e salve o conteúdo em um arquivo de texto (.txt) no computador local.

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a>Para importar o certificado da interface externa do Servidor de Borda

1.  Faça logon como membro do grupo de Administradores no mesmo Servidor de Borda no qual você criou a solicitação de certificado.

2.  No Assistente de Implantação, na página **Implantar Servidor de Borda**, ao lado de **Etapa 3: solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.

3.  Na página **Tarefas de Certificado Disponíveis**, clique em **Importar um certificado de um arquivo. p7b, .pfx ou .cer**.

4.  Na página **Importar Certificado**, clique em **Procurar** para localizar e selecionar o certificado que você solicitou para a interface externa do Servidor de Borda (ou pode digitar o caminho completo e o nome do arquivo). Se o certificado tiver uma chave privada, selecione **Arquivo de certificado contém a chave privada do certificado**  e digite a senha da chave privada. Clique em **Avançar**.

5.  Na página **Importar Resumo de Certificado**, revise o resumo e clique em **Avançar**.

6.  Em **Executando Comandos**, revise os resultados da importação, clique em **Exibir Log** para obter mais informações conforme necessário e clique em **Concluir** para concluir a importação do certificado.

7.  Se você estiver configurando um pool de Servidores de Borda, exporte o certificado com sua chave privada, conforme descrito no procedimento "Para exportar o certificado com a chave particular para Servidores de Borda em um pool" neste tópico. Copie o arquivo de certificado exportado para os outros Servidores de Borda e importe-o para o repositório do computador em cada Servidor de Borda.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Para exportar o certificado com chave privada para os Servidores de Borda em um pool

1.  Faça logon como membro do grupo de Administradores para o mesmo Servidor de Borda no qual você importou o certificado.

2.  Clique em **Iniciar**, em **Executar** e digite **MMC**.

3.  No console MMC (Console de Gerenciamento Microsoft), clique em **Arquivo** e em **Adicionar/Remover Snap-in**.

4.  Em **Adicionar ou Remover Snap-ins**, clique em **Certificados** e em **Adicionar**.

5.  Na caixa de diálogo **Certificados**, selecione **Conta do computador**, clique em **Avançar**, selecione **Computador local: (o computador em que este console está sendo executado)** em **Selecionar Computador**, clique em **Concluir** e em **OK** para concluir a configuração do console MMC.

6.  Clique duas vezes em **Certificados (Computador Local)** para expandir os repositórios de certificados, clique duas vezes em **Pessoais** e em **Certificados**.
    
    <div>
    

    > [!IMPORTANT]  
    > Se não há certificados no repositório de Certificados Pessoais do computador local, não há uma chave privada associada como o certificado importado. Revise as etapas de solicitação e importação. Se o problema persistir, entre em contato com seu administrador da autoridade de certificação ou provedor

    
    </div>

7.  No **Repositório de Certificados Pessoais do computador local**, clique com o botão direito do mouse no certificado que você está exportando, clique em **Todas as Tarefas** e em **Exportar**.

8.  No Assistente para Exportação de Certificados, clique em **Avançar**, selecione **Sim, exportar a chave privada** e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Se a opção <STRONG>Sim, exportar a chave privada</STRONG> não estiver disponível, a chave privada associada a este certificado não foi marcada para exportação. Você precisará solicitar o certificado novamente, garantindo que o certificado esteja marcado para permitir a exportação de chave privada antes de poder continuar com a exportação. Contate seu administrador da autoridade de certificação ou provedor.

    
    </div>

9.  Na caixa de diálogo Exportar formatos de arquivo, selecione **troca de informações\#pessoais – PKCS 12 (. PFX)** e selecione o seguinte:
    
      - Incluir todos os certificados no caminho de certificação, se possível
    
      - Exportar todas as propriedades estendidas
        
        <div>
        

        > [!WARNING]  
        > Quando exportar o certificado de um servidor de Borda, não selecione <STRONG>Excluir a chave privada se a exportação tiver êxito</STRONG>. Selecionar esta opção exigirá que você importe o certificado e a chave privada para este servidor de Borda.

        
        </div>

10. Clique em **Avançar**.

11. Digite uma senha para a chave privada, digite a senha novamente para confirmar e clique em **Avançar**.

12. Digite um caminho e o nome do arquivo para o certificado exportado, usando uma extensão de arquivo .pfx. O caminho deve ser acessível para todos os outros servidores de Borda no pool ou disponível para transportar através de mídia removível - por exemplo, uma unidade flash USB. clique em **Avançar**.

13. Revise o resumo em **Concluindo o Assistente para Exportação de Certificados** e clique em **Concluir**.

14. Na caixa de diálogo de exportação bem-sucedida, clique em **OK**.

15. Importe o arquivo de certificado exportado para outros servidores de Borda seguindo as etapas descritas no procedimento "Para importar o certificado para a interface externa do Servidor de Borda" neste tópico.

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a>Para atribuir o certificado à interface externa do Servidor de Borda

1.  Em cada Servidor de Borda, no Assistente de Implantação, próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.

2.  Na página **Tarefas de Certificado Disponíveis**, clique em **Atribuir um certificado existente**.

3.  Na página **Atribuição de Certificado**, clique em **Certificado de Borda Externa** e marque a caixa de seleção **Usos Avançados de Certificado**.

4.  Na página **Usos Avançados de Certificado**, marque todas as caixas de seleção para atribuir o certificado a todos os usos.

5.  Na página **Repositório de Certificados**, selecione o certificado público que você solicitou e importou para a interface externa do Servidor de Borda.
    
    <div>
    

    > [!NOTE]  
    > Se o certificado solicitado e importado não estiver na lista, um dos métodos de solução de problemas é verificar se o nome da entidade e os nomes alternativos da entidade do certificado atendem a todos os requisitos do certificado. Se você importou manualmente o certificado e a cadeia de certificados em vez de usar os procedimentos anteriores, verifique se o certificado está no repositório de certificados correto (o repositório de certificados do computador, não o repositório de certificados do usuário ou serviço).

    
    </div>

6.  Na página **Resumo da Atribuição de Certificado**, revise suas configurações e clique em **Avançar** para atribuir certificados.

7.  Na página de conclusão do assistente, clique em **Concluir**.

8.  Depois de usar este procedimento para atribuir o certificado de borda, abra o snap-in de Certificados em cada servidor, expanda **Certificados (Computador Local)**, expanda **Pessoais**, clique em **Certificados** e verifique se o certificado está listado no painel de detalhes.

9.  Se sua implantação inclui vários Servidores de Borda, repita este procedimento para cada Servidor de Borda.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

