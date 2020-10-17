---
title: 'Lync Server 2013: Configurando Federação XMPP'
description: 'Lync Server 2013: Configurando Federação XMPP.'
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
ms.openlocfilehash: b8a1fa15e399b0e0596a697420042b7504f8b791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555697"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Configurando a Federação XMPP no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-03_

Para implantar o proxy XMPP no servidor de borda, você deve configurar o servidor de borda para a federação XMPP. Para isso, execute as etapas a seguir.

<div>

## <a name="setting-up-xmpp-federation"></a>Configurando a XMPP

1.  Faça logon no computador onde o assistente de implantação do Lync Server está instalado como um membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins.

2.  No servidor front-end, abra o Assistente para Implantação do Lync Server. Clique em Instalar ou Atualizar o Sistema do Lync Server e depois em Instalar ou Remover os Componentes de Servidor do Lync Server. Clique em Executar Novamente.

3.  Em Instalar componentes do Lync Server, clique em Avançar. A tela de resumo mostrará as ações à medida que forem executadas. Após a conclusão da implantação, clique em Exibir Log para exibir os arquivos de log disponíveis. Clique em Concluir para finalizar a implantação.

4.  No servidor front-end, abra o Assistente para Implantação do Lync Server. Clique em Instalar ou Atualizar o Sistema do Lync Server e depois em Instalar ou Remover os Componentes de Servidor do Lync Server. Clique em Executar Novamente.

5.  Em Instalar componentes do Lync Server, clique em Avançar. A tela de resumo mostrará as ações à medida que forem executadas. Após a conclusão da implantação, clique em Exibir Log para exibir os arquivos de log disponíveis. Clique em Concluir para finalizar a implantação.

6.  No servidor de borda, no Assistente para Implantação, ao lado da Etapa 3: Solicitar, Instalar ou Ceder Certificados, clique em Executar Novamente.
    
    <div class=" ">
    

    > [!TIP]  
    > Se você estiver implantando o servidor de borda pela primeira vez, verá Executar em vez de Executar Novamente.

    
    </div>

7.  Na página Tarefas de Certificado Disponíveis, clique em Criar uma nova solicitação de certificado.

8.  Na página solicitação de certificado, clique em certificado de borda externa.

9.  Na página Solicitação Atrasada ou Imediata, marque a caixa de seleção Preparar a solicitação agora, mas enviá-la mais tarde.

10. Na página arquivo de solicitação de certificado, digite o caminho completo e o nome do arquivo para o qual a solicitação será salva (por exemplo, c: \\ CERT \_ externos \_ Edge. cer).

11. Na página Especificar Modelo de Certificado Alternativo, para usar um modelo diferente do modelo WebServer padrão, marque a caixa de seleção Usar modelo de certificado alternativo para a autoridade de certificação selecionada.

12. Na página Nome e Configurações de Segurança, faça o seguinte:
    
    1.  Em Nome Amigável, digite um nome de exibição para o certificado.
    
    2.  Em Comprimento de bit, especifique o comprimento de bit (normalmente o padrão de 2048).
    
    3.  Verifique se a caixa de seleção Marcar chave privada de certificado como exportável está marcada.

13. Na página Informações da Organização, digite o nome da organização e a unidade organizacional (por exemplo, uma divisão ou um departamento).

14. Na página Informações Geográficas, especifique as informações de localização.

15. Na página Nome da Entidade/Nomes Alternativos da Entidade, as informações a serem preenchidas automaticamente pelo assistente são exibidas. Se nomes alternativos de entidade adicionais forem necessários, especifique-os nas próximas duas etapas.

16. Na página configuração do domínio SIP em nomes alternativos da entidade (SANs), marque a caixa de seleção domínio para adicionar um SIP.\<sipdomain\> entrada à lista de nomes alternativos da entidade.

17. Na página Configurar Nomes Alternativos da Entidade Adicionais, especifique os nomes alternativos de entidade adicionais que sejam necessários.
    
    <div class=" ">
    

    > [!TIP]  
    > Se o proxy XMPP estiver instalado, o nome do domínio (por exemplo, contoso.com) será preenchido nas entradas de SAN por padrão. Se mais entradas forem necessárias, adicione-as nessa etapa.

    
    </div>

18. Na página Resumo da Solicitação, examine as informações de certificado a serem usadas para gerar a solicitação.

19. Após a conclusão da execução dos comandos, você poderá exibir o log ou clicar em Avançar para continuar.

20. Na página Arquivo de Solicitação de Certificado, você pode exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado clicando em Exibir ou fechar o Assistente de Certificado clicando em Concluir.

21. Copie o arquivo de solicitação e envie-o para sua autoridade de certificação pública.

22. Após receber, importar e atribuir o certificado público, você deve parar e reiniciar os serviços do Servidor de Borda. Você faz isso digitando no console do Gerenciamento do Lync Server:
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. Para configurar o DNS para Federação XMPP, adicione o seguinte registro SRV ao DNS externo: \_ XMPP-Server. \_ TCP.\<domain name\> O registro SRV será resolvido para o FQDN de borda de acesso do servidor de borda, com um valor de porta de 5269. Além disso, configure um registro de host "A" (por exemplo, xmpp.contoso.com) que aponte para o endereço IP do servidor de borda de acesso.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Se você tiver pools de borda em vários sites, é recomendável que adicione vários registros SRV para federação XMPP. Adicione um registro SRV para cada pool de borda de sua organização e atribua a cada um desses registros SRV uma prioridade diferente. Quando todos os pools de borda estiverem em execução, as solicitações XMPP serão todas manipuladas pelo pool de borda com a maior prioridade, mas, se esse pool de borda ficar inoperante, você não precisará adicionar um novo registro SRV para recuperar a funcionalidade de federação XMPP.

    
    </div>

24. Configure uma nova política de acesso externo para habilitar todos os usuários abrindo o Shell de Gerenciamento do Lync Server no front-end e digitando:
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Habilite o acesso XMPP para usuários externos digitando:
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. No servidor de borda onde o proxy XMPP está implantado, abra um prompt de comando ou uma interface de linha de comando do Windows PowerShell™ e digite o seguinte:
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    O comando **netstat – ano** é um comando de estatísticas de rede, a solicitação de parâmetros **– ano** em que netstat exibe todas as conexões e portas de escuta, address e Ports são exibidos em um formato numérico e que a ID de processo de propriedade é associada a cada conexão. O caractere **|** define um pipe para o próximo comando, **findstr**ou localizar cadeia de caracteres. O número 5269 e 23456 que é passado para findstr como um parâmetro instrui o findstr a Pesquisar a saída do netstat para as cadeias de caracteres 5269 e 23456. Se o XMPP estiver configurado corretamente, o resultado dos comandos deverá resultar em conexões estabelecidas e estabelecidas, tanto na interface externa (porta 5269) quanto nas interfaces internas (porta 23456) do servidor de borda.
    
    Se os comandos não retornarem as portas estabelecidas ou de escuta em 5269 e 23456, verifique o seguinte:

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Solucionando problemas da federação XMPP

1.  Para determinar se o proxy XMPP está em execução, faça o seguinte:

2.  Faça logon no servidor de borda que está executando o serviço do proxy XMPP como membro do grupo de administrador local.

3.  Clique em **Iniciar**, em **Todos os Programas**, em **Ferramentas Administrativas** e em **Serviços**

4.  Em Serviços, localize Proxy do Gateway de Tradução XMPP do Lync Server. O serviço deverá estar no estado **Iniciado**. Se ele não estiver iniciado, clique no ícone **Iniciar** na barra de ferramentas. O ícone se parece com uma seta verde apontando para a direita.

5.  Confirme se o serviço mudou para **Iniciado**. Se ele tiver sido iniciado com êxito, feche **Serviços** e continue o procedimento.
    
    Se o serviço não tiver sido iniciado com êxito, nas Ferramentas Administrativas, abra o Visualizador de Eventos e consulte os erros e avisos na parte **Lync Server** em **Logs de Aplicativos e Serviços**.

6.  Depois que o serviço **Proxy do Gateway de Tradução XMPP do Lync Server** estiver em execução, verifique novamente os comandos netstat usados anteriormente. Se você não estiver vendo sessões estabelecidas ou de escuta, verifique se a **rota de Federação do XMPP** está configurada corretamente no construtor de topologias

7.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

8.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

9.  No construtor de topologias, selecione o site para a rota de Federação do XMPP e revise para confirmar que a **atribuição de rota de Federação do site** para a **Federação XMPP** mostra o servidor de borda ou o pool de borda como a atribuição de rota de Federação do XMPP selecionada.
    
    Se a atribuição de rota estiver incorreta ou não estiver definida, clique com o botão direito do mouse no site e depois em **Editar Propriedades**. Marque a caixa de seleção Federação XMPP e, em seguida, selecione o servidor de borda ou o pool de borda correto.

10. Publique a topologia. Para obter detalhes, consulte [Publish Your Topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Embora não seja obrigatório e normalmente não seja necessário, você pode precisar reiniciar os servidores de borda

    
    </div>

11. Usando o processo netstat usado anteriormente, confirme se o servidor de borda agora está escutando ou estabeleceu sessões na porta 5269 e na porta 23456.

12. Se as sessões esperadas ainda não forem exibidas, verifique o Visualizador de Eventos para ver se há possíveis causas para o problema de comunicação.

</div>

<div>

## <a name="see-also"></a>Confira também


[Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gerenciar parceiros federados do XMPP no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

