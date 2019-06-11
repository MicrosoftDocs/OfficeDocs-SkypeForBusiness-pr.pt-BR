---
title: Configurar rotas de federação e tráfego de mídia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836784"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar rotas de federação e tráfego de mídia

 


A Federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários de organizações separadas se comuniquem entre os limites da rede. Depois de migrar para o pool piloto do Lync Server 2013, você precisará fazer a transição da rota de Federação de seus servidores do Microsoft Office Communications Server 2007 R2 Edge para a rota de Federação do seu Lync Server 2013 Servers Edge.

Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do servidor de borda do Office Communications Server 2007 R2 e do diretor para o servidor do Lync Server 2013 para uma implantação de um único site.


> [!IMPORTANT]  
> Alterar a rota de Federação e a rota de tráfego de mídia requer que você agende o tempo de inatividade de manutenção dos servidores do Lync Server 2013 e do Office Communications Server 2007 R2 Edge. Esse processo de transição inteiro também significa que o acesso federado estará indisponível para a duração da interrupção. Você deve programar o tempo de inatividade para um horário em que espera a atividade do usuário mínima. Você também deve fornecer uma notificação suficiente para seus usuários finais. Planeje-se adequadamente para esta interrupção e defina as expectativas adequadas dentro da sua organização.




> [!IMPORTANT]  
> Se seu servidor herdado do Office Communications Server 2007 R2 estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda a/V, os procedimentos desta seção serão usados para fazer a transição da configuração de Federação para um Lync Server Não há suporte para o servidor de borda do 2013. Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, primeiro você deve migrar todos os seus usuários do Office Communications Server 2007 R2 para o Lync Server 2013 e, em seguida, encerrar o servidor do Office Communications Server 2007 R2 Edge Server antes de habilitar a Federação em o servidor de borda do Lync Server 2013. Para detalhes, consulte os seguintes tópicos: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Mover usuários restantes para Lync Server 2013</A></P>
> <LI>
> <P>"Remover servidores e funções de servidor" em<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Se a sua Federação do XMPP for roteada por meio de um servidor de borda do Lync Server 2013, os usuários herdados do Office Communications Server 2007 R2 não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para as políticas do Lync Server 2013, XMPP e os certificados foram configurados, o parceiro federado do XMPP foi configurado no Lync Server 2013 e, por último, as entradas DNS foram atualizadas.



Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio. Também é possível delegar os direitos de usuário e permissões adequados para adicionar funções de servidor. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition Server. Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Para remover a associação de Federação herdada dos sites do Lync Server 2013

1.  Abra a topologia do pool piloto usando o construtor de topologias.

2.  No painel esquerdo, navegue até o nó do site.

3.  Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.

4.  Selecione **roteiro de Federação** no painel esquerdo.

5.  Em atribuição de rota de Federação do site, desmarque a caixa de seleção ao lado de **habilitar Federação SIP** para desabilitar a rota de Federação por meio do **BackCompatSite**.
    
    ![Caixa de diálogo Editar propriedades, roteiro de Federação] (images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Caixa de diálogo Editar propriedades, roteiro de Federação")

6.  Clique em **OK** para fechar a página Editar propriedades.

7.  No **Construtor**de topologias, selecione o nó superior do **Lync Server**.

8.  No menu **ação** , clique em **publicar topologia** e conclua o assistente.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o servidor de borda herdado como um servidor de borda não federativo

1.  No **Construtor de topologia**, no menu **ação** , clique em **mesclar topologia do Office Communications Server 2007 R2**.

2.  Clique em **Avançar** para continuar.

3.  Na **configuração especificar borda**, selecione o **FQDN interno do servidor de borda** que está configurado atualmente para Federação e clique em **alterar**.
    
    ![Mescle a topologia do OCS 2007 R2, especifique a configuração de borda] (images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Mescle a topologia do OCS 2007 R2, especifique a configuração de borda")

4.  Clique em **Avançar** e aceite as configurações padrão até chegar à página **especificar borda externa** :
    
    ![Construtor de topologias especificar página de borda externa] (images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Construtor de topologias especificar página de borda externa")

5.  Em **especificar borda externa**, desmarque a caixa de seleção **este pool de bordas é usado para a Federação e conectividade de im pública** . Isso irá remover a associação de Federação com o BackCompatSite.
    

    > [!IMPORTANT]  
    > Esta etapa é importante. Você deve desmarcar essa opção para remover a associação de Federação herdada.



6.  Clique em **Avançar** e aceite as configurações padrão das páginas restantes do assistente.

7.  Em **Resumo**, clique em **Avançar** para começar a mesclar as topologias.

8.  Na coluna **status** , verifique se o valor é **êxito**e clique em **concluir** para fechar o assistente.

9.  No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.

10. Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.
    
    ![Construtor de topologias com o site exibido após] a mesclagem (images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Construtor de topologias com o site exibido após") a mesclagem
    
    Como mostrado na figura anterior, a **Federação SIP** localizada em **atribuição de rota de Federação do site** está definida como **desabilitada**.

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Para configurar certificados no servidor de borda do Lync Server 2013

1.  Exportar o certificado de proxy de acesso externo, com a chave privada, do servidor de borda do Office Communications Server 2007 R2 herdado.

2.  No servidor de borda do Lync Server 2013, importe o certificado de proxy externo do Access da etapa anterior.

3.  Atribua o certificado de proxy externo do Access à interface externa do Lync Server 2013 do servidor de borda.

4.  O certificado de interface interna do servidor de borda do Lync Server 2013 não deve ser alterado.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Para alterar a rota de Federação do Office Communications Server 2007 R2 para usar o servidor de borda 2013 do Lync Server

1.  No servidor do Office Communications Server 2007 R2 Standard Edition ou no servidor front-end, abra a ferramenta administrativa do Office Communications Server 2007 R2.

2.  No painel esquerdo, expanda o nó superior e clique com o botão direito do mouse no nó da **floresta** . Selecione **Propriedades**e, em seguida, clique em **propriedades globais**.

3.  Clique na guia **Federação** .

4.  Marque a caixa de seleção para habilitar a conectividade de mensagens de chat pública e de Federação.

5.  Digite o FQDN do servidor de borda do Lync Server 2013 e, em seguida, clique em **OK**.
    
    ![Propriedades globais do OCS, guia Federação] (images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriedades globais do OCS, guia Federação")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Para ativar a Federação do servidor de borda do Lync Server 2013

1.  No construtor de topologias, no painel esquerdo, navegue até o nó de **pools de borda** do Lync Server 2013.

2.  Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**.
    

    > [!NOTE]  
    > A Federação só pode ser habilitada para um único pool de bordas. Se você tiver vários pools de bordas, selecione um para usá-lo como o pool de bordas de Federação.



3.  Na página **geral** , marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** .
    
    ![Editar propriedades, geral, habilitar Federação de borda] (images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Editar propriedades, geral, habilitar Federação de borda")

4.  Clique em **OK** para fechar a página Editar propriedades.

5.  Em seguida, navegue até o nó do site.

6.  Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.

7.  No painel esquerdo, clique em **rota de Federação**.

8.  Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Lync Server 2013 listado.

9.  Clique em **OK** para fechar a página **Editar propriedades** .
    
    ![Editar propriedades, geral, associar pool de bordas] (images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propriedades, geral, associar pool de bordas")
    
    Para implantações em vários locais, conclua este procedimento em cada site.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Para configurar o caminho da mídia de saída do servidor de borda do Lync Server 2013

1.  No **Construtor**de topologias, navegue até o pool do Lync Server 2013 abaixo de **servidores front-end da edição padrão** ou **pools front-ends do Enterprise Edition**.

2.  Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.

3.  Na seção **associações** , marque a caixa de seleção **associar o pool de bordas (para componentes de mídia)** .

4.  Na caixa suspensa, selecione o servidor de borda do Lync Server 2013.
    
    ![Caixa de diálogo Editar propriedades, associar pool de bordas] (images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Caixa de diálogo Editar propriedades, associar pool de bordas")

5.  Clique em **OK** para fechar a página **Editar propriedades** .

## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do servidor de borda

1.  No **Construtor**de topologias, selecione o nó superior do **Lync Server**.

2.  No menu **ação** , selecione **publicar topologia** e conclua o assistente.

3.  Aguarde até que a replicação do Active Directory ocorra em todos os pools da implantação.
    

    > [!NOTE]  
    > Você pode ver a seguinte mensagem:<BR><STRONG>Aviso: a topologia contém mais de um servidor de borda federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um servidor de borda seria usado ativamente para Federação. Verifique se o registro SRV DNS externo aponta para o servidor de borda correto. Se você quiser implantar várias bordas de servidor de borda para ativar simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Office Communications Server 2007 R2 ou o Lync Server. Verifique se o registro SRV DNS externo lista todos os servidores de borda habilitados para Federação.</STRONG><BR>Este aviso é esperado e pode ser ignorado com segurança.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>Para verificar a Federação e o acesso remoto para usuários externos

1.  No servidor de front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.

2.  Para verificar o status da Federação e do acesso remoto, na linha de comando, digite o seguinte:
    
        Get-CsAccessEdgeConfiguration

3.  Para habilitar a Federação e o acesso remoto, na linha de comando, digite o seguinte:
    
        Set-CsAccessEdgeConfiguration
    
    Para obter mais informações sobre esses cmdlets, consulte os tópicos a seguir: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) e [set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).

4.  Aguarde até que a replicação seja concluída antes de colocar os servidores de borda do Lync Server 2013 online e testar a Federação e o acesso externo.

## <a name="to-configure-lync-server-2013-edge-server"></a>Para configurar o servidor de borda do Lync Server 2013

1.  Reúna todos os servidores do Lync Server 2013 Edge online.

2.  Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor do Lync 2013, em vez do servidor de borda herdado.
    

    > [!NOTE]  
    > Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS A para Federação para resolver o novo servidor de borda de acesso do Lync Server. Para fazer isso com interrupção mínima, reduza o valor TTL do FQDN do servidor de borda de acesso externo do Lync Server, para que, quando o DNS for atualizado para apontar para o novo servidor de borda de acesso do Lync Server, a Federação e o acesso remoto sejam atualizados rapidamente.



3.  Em seguida, interrompa a **borda de acesso do Lync Server** de cada computador do servidor de borda.

4.  Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.

5.  Na lista serviços, localize a **borda de acesso do Office Communications Server**.

6.  Clique com o botão direito do mouse no nome dos serviços e, em seguida, selecione **parar** para interromper o serviço.

7.  Defina o tipo de inicialização **** como desabilitado.

8.  Clique em **OK** para fechar a janela **Propriedades** .

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>Para testar a conectividade de usuários externos e acesso externo

  - Usuários de pelo menos um domínio federado, um usuário interno no Lync Server 2013 e um usuário no Office Communications Server 2007 R2. Testar mensagens instantâneas (IM), presença, áudio/vídeo (A/V) e compartilhamento da área de trabalho.

  - Os usuários de cada provedor de serviço de mensagens de chat público compatível com a sua organização (e para a qual o provisionamento foi concluído) se comunicam com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.

  - Verifique se usuários anônimos podem participar de conferências.

  - Um usuário hospedado no Office Communications Server 2007 R2 usando acesso de usuário remoto (conectando-se ao Office Communications Server 2007 R2 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2. Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.

  - Um usuário hospedado no Lync Server 2013 usando acesso de usuário remoto (fazendo logon no Lync Server 2013 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2. Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.

