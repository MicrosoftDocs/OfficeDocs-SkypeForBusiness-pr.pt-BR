---
title: Configure o tráfego de mídia e rotas de federação
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fc7359a21d60c0c77028491af9fccdf21991c58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136088"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configure o tráfego de mídia e rotas de federação

 


A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Após migrar para o pool piloto do Lync Server 2013, você precisará fazer a transição da rota de Federação de seus servidores de borda do Microsoft Office Communications Server 2007 R2 para a rota de Federação de seus servidores de borda do Lync Server 2013.

Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do servidor de borda do Office Communications Server 2007 R2 e do diretor para o servidor de borda do Lync Server 2013, para uma implantação de site único.


> [!IMPORTANT]  
> Alterar a rota de Federação e a rota de tráfego de mídia exige que você agende o tempo de inatividade de manutenção para os servidores de borda do Lync Server 2013 e do Office Communications Server 2007 R2. Todo esse processo de transição também significa que o acesso federado não estará disponível durante a interrupção. Agende o tempo de inatividade para um período no qual você espera o mínimo de atividade de usuário. Você também deve fornecer notificações suficientes para seus usuários finais. Planeje-se adequadamente para essa interrupção e defina as expectativas apropriadas dentro de sua organização.




> [!IMPORTANT]  
> Se o servidor de borda do Office Communications Server 2007 R2 herdado estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda A/V, os procedimentos desta seção para fazer a transição da configuração de Federação para um servidor de borda do Lync Server 2013 não têm suporte. Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, você deverá primeiro migrar todos os usuários do Office Communications Server 2007 R2 para o Lync Server 2013 e, em seguida, encerrar o servidor de borda do Office Communications Server 2007 R2 antes de habilitar a Federação no o servidor de borda do Lync Server 2013. Para obter informações detalhadas, consulte os seguintes tópicos: 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Mover os usuários restantes para o Lync Server 2013</A></P>
> <LI>
> <P>"Remover servidores e funções de servidor" em<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> Se sua Federação do XMPP for encaminhada por um servidor de borda do Lync Server 2013, os usuários herdados do Office Communications Server 2007 R2 não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Lync Server 2013, políticas do XMPP e certificados foram configurados, o parceiro federado XMPP foi configurado no Lync Server 2013 e, por fim, as entradas DNS foram atualizadas.



Para publicar, habilitar ou desabilitar com êxito uma topologia ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e Administradores de Domínio. Também é possível delegar os direitos e permissões apropriados de usuário para adição de funções de servidor. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition. Para fazer outras alterações na configuração, apenas a associação ao grupo RTCUniversalServerAdmins é necessária.

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Para remover a associação de federação herdada de sites do Lync Server 2013

1.  Abra a topologia do pool piloto usando o Construtor de Topologia

2.  No painel esquerdo, navegue até o nó do site.

3.  Clique com o botão direito no site e clique em **Editar propriedades**.

4.  Selecione **Rota de federação** no painel esquerdo.

5.  Em Atribuição de rota de federação de local, desmarque a caixa de seleção ao lado de **Habilitar federação SIP** para desabilitar a rota de federação pelo **BackCompatSite**.
    
    ![Caixa de diálogo Editar propriedades, rota de Federação](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Caixa de diálogo Editar propriedades, rota de Federação")

6.  Clique em **OK** para fechar a página Editar Propriedades.

7.  A partir do **Construtor de Topologia**, selecione o nó superior **Lync Server**.

8.  No menu **Ações**, clique em **Publicar topologia** e complete o assistente.

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o Servidor de Borda herdado como um Servidor de Borda não federado

1.  No **Construtor de Topologia**, no painel **Ações**, clique em **Mesclar topologia do Office Communications Server 2007 R2**.

2.  Clique em **Avançar** para continuar.

3.  Em **Especificar Configuração de Borda**, selecione o **FQDN Interno do Servidor de Borda** configurado atualmente para federação e clique em **Alterar**.
    
    ![Mesclar a topologia do OCS 2007 R2, especificar configuração de borda](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Mesclar a topologia do OCS 2007 R2, especificar configuração de borda")

4.  Clique em **Avançar** e aceite as configurações padrão até chegar à página **Especificar Borda Externa**:
    
    ![Página especificar borda externa do construtor de topologia](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Página especificar borda externa do construtor de topologia")

5.  Em **Especificar Borda Externa**, desmarque a caixa de seleção **Este pool de Borda é usado para conectividade de IM pública e de _federação**. Isso removerá a associação de federação com o BackCompatSite.
    

    > [!IMPORTANT]  
    > Esta etapa é importante. É necessário desmarcar essa opção para remover a associação de federação herdada.



6.  Clique em **Avançar** e aceite as configurações padrão das páginas restantes do assistente.

7.  Em **Resumo**, clique em **Avançar** para começar a mesclar as topologias.

8.  Na coluna **status** , verifique se o valor é **êxito**e clique em **concluir** para fechar o assistente.

9.  No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.

10. Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente.
    
    ![Construtor de topologias com o site exibido após a mesclagem](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Construtor de topologias com o site exibido após a mesclagem")
    
    Conforme exibido na figura anterior, a  **Federação SIP** localizada na **Atribuição de rota de federação de local** está definida como **Desabilitada**

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Para configurar certificados no Servidor de Borda do Lync Server 2013

1.  Exporte o certificado de proxy de acesso externo, com a chave privada, do servidor de borda do Office Communications Server 2007 R2 herdado.

2.  No servidor de borda do Lync Server 2013, importe o certificado externo do proxy de acesso da etapa anterior.

3.  Atribua o certificado externo do proxy de acesso à interface externa do Lync Server 2013 do servidor de borda.

4.  O certificado de interface interna do servidor de borda do Lync Server 2013 não deve ser alterado.

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Para alterar a rota de federação do Office Communications Server 2007 R2 para usar o Servidor de Borda do Lync Server 2013

1.  No servidor do Office Communications Server 2007 R2 Standard Edition ou servidor front-end, abra a ferramenta administrativa do Office Communications Server 2007 R2.

2.  No painel esquerdo, expanda o nó superior e clique com o botão direito do mouse no nó **Floresta**. Selecione **Propriedades** e clique em **Propriedades Globais**.

3.  Clique na guia **Federação**.

4.  Marque a caixa de seleção para habilitar a federação e a conectividade de IM pública.

5.  Insira o FQDN do servidor de borda do Lync Server 2013 e clique em **OK**.
    
    ![Propriedades globais do OCS, guia Federação](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriedades globais do OCS, guia Federação")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Para ativar a federação do Servidor de Borda do Lync Server 2013

1.  No construtor de topologias, no painel esquerdo, navegue até o nó **pools de borda** do Lync Server 2013.

2.  Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**.
    

    > [!NOTE]  
    > A Federação só pode ser habilitada para um único pool de borda. Se você tiver vários pools de borda, selecione um para usar como o pool de Borda de federação.



3.  Na página **Geral**, marque a caixa de seleção **Habilitar federação para este pool de Borda (Porta 5061)**.
    
    ![Editar propriedades, geral, habilitar Federação de borda](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Editar propriedades, geral, habilitar Federação de borda")

4.  Clique em **OK** para fechar a página Editar Propriedades.

5.  Em seguida, navegue até o nó do site.

6.  Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.

7.  No painel esquerdo, clique em **Rota de federação**.

8.  Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Lync Server 2013 listado.

9.  Clique em **OK** para fechar a página **Editar Propriedades**.
    
    ![Editar propriedades, geral, associar pool de borda](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propriedades, geral, associar pool de borda")
    
    Para implantações entre vários locais, realize este procedimento para cada local.

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Para configurar o caminho de mídia de saída do Servidor de Borda do Lync Server 2013

1.  No **Construtor de topologias**, navegue até o pool do Lync Server 2013 abaixo de **servidores front-end Standard Edition** ou **pools de front-ends Enterprise Edition**.

2.  Clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.

3.  Na seção **Associações**, marque a caixa de seleção **Associar pool de Borda (para componentes de mídia)**.

4.  Na caixa suspensa, selecione o servidor de borda do Lync Server 2013.
    
    ![Caixa de diálogo Editar propriedades, associar pool de borda](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Caixa de diálogo Editar propriedades, associar pool de borda")

5.  Clique em **OK** para fechar a página **Editar Propriedades**.

## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do Servidor de Borda

1.  A partir do **Construtor de Topologias**, selecione o nó superior **Lync Server**.

2.  No menu **Ações**, selecione **Publicar Topologia** e conclua o assistente.

3.  Aguarde que a replicação do Active Directory ocorra em todos os pools na implantação.
    

    > [!NOTE]  
    > Talvez você veja a seguinte mensagem:<BR><STRONG>Aviso: a topologia contém mais de um Servidor de Borda Federado. Isso pode ocorrer durante a migração para uma versão superior do produto. Nesse caso, somente um Servidor de Borda seria ativamente usado para federação. Verifique se o registro SRV DNS externo aponta para o Servidor de Borda correto. Se desejar que vários Servidores de Borda de federação permaneçam ativos simultaneamente (isto é, não em um cenário de migração), verifique se todos os parceiros federados estão usando o Office Comunications Server 2007 R2 ou superior e certifique-se de que o registro SRV DNS externo liste todos os Servidores de Borda ativamente para federação.</STRONG><BR>Esse aviso é esperado e pode ser ignorado com segurança.



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>Para verificar o acesso remoto e de federação para usuários externos

1.  No servidor front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.

2.  Para verificar o status do acesso remoto e de federação, digite o seguinte na linha de comando:
    
        Get-CsAccessEdgeConfiguration

3.  Para habilitar o acesso remoto e de federação, digite o seguinte na linha de comando:
    
        Set-CsAccessEdgeConfiguration
    
    Para obter mais informações sobre esses cmdlets, consulte os seguintes tópicos: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) e [set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).

4.  Aguarde até que a replicação seja concluída antes de colocar os servidores de borda do Lync Server 2013 online e testar a Federação e o acesso externo.

## <a name="to-configure-lync-server-2013-edge-server"></a>Para configurar o Servidor de Borda do Lync Server 2013

1.  Coloque todos os servidores de borda do Lync Server 2013 online.

2.  Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor de borda do Lync Server 2013, em vez do servidor de borda herdado.
    

    > [!NOTE]  
    > Se você não tem um balanceador de carga de hardware, você precisa atualizar o registro A do DNS para a federação resolver o novo servidor de borda de acesso do Lync Server. Para realizar essa tarefa com o mínimo de interrupção, reduza o valor de TTL do FQDN da Borda de Acesso do Lync Server externo para que quando o DNS for atualizado para apontar para a nova Borda de Acesso do Lync Server, a federação e o acesso remoto sejam atualizado rapidamente.



3.  Em seguida, pare a **borda de acesso do Lync Server** de cada computador do servidor de borda.

4.  Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.

5.  Na lista de serviços, encontre **Borda de Acesso do Office Communications Server**.

6.  Clique com o botão direito do mouse no nome dos serviços e selecione **Parar** para parar o serviço.

7.  Defina o tipo de inicialização para **Desativado**.

8.  Clique em **Ok** para fechar a janela **Propriedades**.

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>Para testar a conectividade de usuários externos e o acesso externo

  - Usuários de pelo menos um domínio federado, um usuário interno no Lync Server 2013 e um usuário no Office Communications Server 2007 R2. Teste as mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.

  - Os usuários de cada provedor de serviços públicos de IM que sua organização suporta (e para o qual o provisionamento foi concluído) comunicando-se com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.

  - Verifique se os usuários anônimos podem participar de conferências.

  - Um usuário hospedado no Office Communications Server 2007 R2 usando acesso de usuário remoto (fazendo logon no Office Communications Server 2007 R2 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2. Testar a IM, presença, A/V e compartilhamento de área de trabalho.

  - Um usuário hospedado no Lync Server 2013 usando acesso de usuário remoto (fazendo logon no Lync Server 2013 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2. Testar a IM, presença, A/V e compartilhamento de área de trabalho.

