---
title: 'Lync Server 2013: Configurando federação de XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Configurando federação de XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-03_

Para implantar o proxy XMPP no servidor de borda, você deve configurar o servidor de borda para a Federação do XMPP. Para fazer isso, siga as etapas a seguir.

<div>

## <a name="setting-up-xmpp-federation"></a>Configurando a Federação do XMPP

1.  Faça logon no computador em que o assistente de implantação do Lync Server está instalado como membro do grupo Domain admins e do grupo RTCUniversalServerAdmins.

2.  No servidor front-end, abra o assistente de implantação do Lync Server. Clique em instalar ou atualizar o Lync Server System e, em seguida, clique em configurar ou remover componentes do Lync Server. Clique em executar novamente.

3.  Em configurar componentes do Lync Server, clique em Avançar. A tela Resumo mostrará as ações conforme elas são executadas. Depois que a implantação for concluída, clique em Exibir log para exibir os arquivos de log disponíveis. Clique em concluir para concluir a implantação.

4.  No servidor de borda, abra o assistente de implantação do Lync Server. Clique em instalar ou atualizar o Lync Server System e, em seguida, clique em configurar ou remover componentes do Lync Server. Clique em executar novamente.

5.  Em configurar componentes do Lync Server, clique em Avançar. A tela Resumo mostrará as ações conforme elas são executadas. Depois que a implantação for concluída, clique em Exibir log para exibir os arquivos de log disponíveis. Clique em concluir para concluir a implantação.

6.  No servidor de borda, no assistente de implantação, ao lado da etapa 3: solicitar, instalar ou atribuir certificados, clique novamente em executar.
    
    <div class=" ">
    

    > [!TIP]  
    > Se você estiver implantando o servidor de borda pela primeira vez, você verá executar novamente em vez de executar novamente.

    
    </div>

7.  Na página Tarefas de Certificado Disponíveis, clique em  Criar uma nova solicitação de certificado.

8.  Na página solicitação de certificado, clique em certificado de borda externa.

9.  Na página solicitação atrasada ou imediata, marque a caixa de seleção preparar a solicitação agora, mas enviá-la mais tarde.

10. Na página arquivo de solicitação de certificado, digite o caminho completo e o nome do arquivo para o qual a solicitação deve ser salva (por exemplo, c:\\CERT\_guia\_Edge. cer).

11. Na página especificar modelo de certificado alternativo, para usar um modelo diferente do modelo padrão do webserver, marque a caixa de seleção usar modelo de certificado alternativo para a autoridade de certificação selecionada.

12. Na página  Nome e Configurações de Segurança, siga estes procedimentos:
    
    1.  Em nome amigável, digite um nome de exibição para o certificado
    
    2.  Em comprimento de bit, especifique o comprimento do bit (geralmente, o padrão de 2048)
    
    3.  Verifique se a caixa de seleção Marcar chave privada de certificado como exportável está marcada

13. Na página informações da organização, digite o nome da organização e da unidade organizacional (por exemplo, uma divisão ou um departamento)

14. Na página informações geográficas, especifique as informações de localização

15. Na página nome do assunto/nomes alternativos de assunto, as informações a serem automaticamente preenchidas pelo assistente serão exibidas. Se forem necessários nomes alternativos de entidades adicionais, você os especificará nas duas próximas etapas

16. Na configuração de domínio SIP na página de nomes alternativos de entidades (SANs), marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de assunto.

17. Na página Configurar nomes alternativos de entidades adicionais, especifique os nomes alternativos de entidades adicionais necessários
    
    <div class=" ">
    

    > [!TIP]  
    > Se o proxy XMPP estiver instalado, por padrão, o nome de domínio (como contoso.com) será preenchido nas entradas de SAN. Se você precisar de mais entradas, adicione-as nesta etapa.

    
    </div>

18. Na página Resumo da solicitação, examine as informações do certificado a serem usadas para gerar a solicitação.

19. Após a conclusão da execução dos comandos, você pode exibir o log ou clicar em avançar para continuar.

20. Na página arquivo de solicitação de certificado, você pode exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado clicando em exibir ou em sair do assistente de certificado clicando em concluir.

21. Copie o arquivo de solicitação e envie para sua autoridade de certificação pública.

22. Depois de receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do servidor de borda. Para fazer isso, digite no console de gerenciamento do Lync Server:
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. Para configurar o DNS para a Federação do XMPP, adicione o seguinte registro SRV para DNS\_externo: XMPP-Server. \_TCP. \<nome\> do domínio o registro SRV será resolvido para o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269. Além disso, você configura um registro de host ' A ' (por exemplo, xmpp.contoso.com) que aponta para o endereço IP do servidor de borda de acesso.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Se você tiver pools de bordas em vários sites, recomendamos que adicione vários registros SRV para a Federação do XMPP. Adicione um registro SRV para cada pool de bordas em sua organização e dê a cada um desses registros uma prioridade diferente. Quando todos os pools de bordas estiverem em execução, as solicitações de XMPP serão manipuladas pelo pool de bordas com a primeira prioridade, mas, se esse pool de bordas cair, você não terá que adicionar um novo registro SRV para recuperar a funcionalidade de Federação do XMPP.

    
    </div>

24. Configure uma nova política de acesso externo para permitir que todos os usuários abram o Shell de gerenciamento do Lync Server no front-end e digitem:
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Habilite o acesso do XMPP para usuários externos digitando:
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. No servidor de borda em que o proxy XMPP está implantado, abra um prompt de comando ou uma interface de linha de comando™ do Windows PowerShell e digite o seguinte:
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    O comando **netstat – ano** é um comando de estatísticas de rede, os parâmetros – pedido do **ano** em que o netstat exibe todas as conexões e portas de escuta, endereço e portas são exibidos em uma forma numérica e se a ID do processo de propriedade está associada a cada conexão. O caractere **|** define um pipe para o próximo comando, **findstr**ou localizar cadeia de caracteres. O número 5269 e 23456 que é passado para findstr como parâmetro instrui findstr para pesquisar a saída do netstat para as cadeias de caracteres 5269 e 23456. Se XMPP estiver configurado corretamente, o resultado dos comandos deve resultar em conexões de escuta e estabelecidas, ambas nas interfaces externa (porta 5269) e interna (porta 23456) do servidor de borda.
    
    Se os comandos não retornam portas estabelecidas ou em escuta no 5269 e no 23456, verifique o seguinte:

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Solução de problemas de Federação do XMPP

1.  Para determinar se o proxy XMPP está em execução, faça o seguinte:

2.  Faça logon no servidor de borda que está executando o serviço de proxy XMPP como membro do grupo administrador local.

3.  Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e em **Serviços**

4.  Em serviços, localize o Lync Server XMPP de converter proxy de gateway. O serviço deve estar no estado **inicial** . Se não for iniciado, clique no ícone **Iniciar** na barra de ferramentas. O ícone aparece como uma seta verde, apontando para a direita.

5.  Confirme se o serviço mudou para **iniciado**. Se ele tiver começado com êxito, feche os **Serviços** e continue.
    
    Se o serviço não foi iniciado com êxito, em ferramentas administrativas, abra o Visualizador de eventos e consulte os avisos e erros na parte do **Lync Server** em **logs de aplicativos e serviços**.

6.  Depois que o serviço do **Gateway de conversão do Lync Server XMPP** estiver em execução, verifique novamente os comandos netstat usados anteriormente. Se você não estiver vendo sessões estabelecidas ou em escuta, verifique se a **rota de Federação do XMPP** está configurada corretamente no construtor de topologias

7.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

8.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

9.  No construtor de topologias, selecione o site para a rota de Federação do XMPP e a revisão para confirmar que a **atribuição de rota de Federação do site** para a **Federação XMPP** mostra o servidor de borda ou o pool de bordas como a atribuição de rota de Federação do XMPP selecionada.
    
    Se a atribuição de roteiro estiver incorreta ou não estiver definida, clique com o botão direito do mouse no site e clique em **Editar propriedades**. Marque a caixa de seleção Federação do XMPP e selecione o servidor de borda ou o pool de bordas correto.

10. Publique a topologia. Para obter detalhes, consulte [publicar sua topologia no Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Embora não seja necessário e normalmente não é necessário, você pode descobrir que precisará reiniciar os servidores de borda

    
    </div>

11. Usando o processo netstat usado anteriormente, confirme se o servidor de borda agora está ouvindo ou se estabeleceu sessões na porta 5269 e na porta 23456.

12. Se você ainda não estiver vendo as sessões esperadas, verifique o Visualizador de eventos para possíveis causas de contribuição para o problema de comunicação.

</div>

<div>

## <a name="see-also"></a>Confira também


[Exemplo de configuração de XMPP no Lync Server 2013 – federação XMPP com Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gerenciar parceiros XMPP federados no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

