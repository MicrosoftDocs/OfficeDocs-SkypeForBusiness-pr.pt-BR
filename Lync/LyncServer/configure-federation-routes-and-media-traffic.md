---
title: Configure o tráfego de mídia e rotas de federação
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b07e0bfe62fe6d09521d1f9d5dc2d84aa975d5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503348"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configure o tráfego de mídia e rotas de federação

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-15_

A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Após migrar para o pool piloto do Lync Server 2013, você precisará fazer a transição da rota de Federação de seus servidores de borda do Lync Server 2010 para a rota de Federação de seus servidores de borda do Lync Server 2013.

Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do seu servidor de borda e diretor do Lync Server 2010 para o servidor de borda do Lync Server 2013, para uma implantação de site único.

<div>


> [!IMPORTANT]  
> Alterar a rota de Federação e a rota de tráfego de mídia exige que você agende o tempo de inatividade de manutenção para os servidores de borda do Lync Server 2013 e Lync Server 2010. Todo esse processo de transição também significa que o acesso federado não estará disponível durante a interrupção. Agende o tempo de inatividade para um período no qual você espera o mínimo de atividade de usuário. Você também deve fornecer notificações suficientes para seus usuários finais. Planeje-se adequadamente para essa interrupção e defina as expectativas apropriadas dentro de sua organização.



</div>

<div>


> [!IMPORTANT]  
> Se o servidor de borda do Lync Server 2010 herdado estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda A/V, não haverá suporte para os procedimentos desta seção. Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, você deverá primeiro migrar todos os seus usuários do Lync Server 2010 para o Lync Server 2013 e, em seguida, encerrar o servidor de borda do Lync Server 2010 antes de habilitar a Federação no servidor de borda do Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> Se sua Federação do XMPP for encaminhada por um servidor de borda do Lync Server 2013, os usuários herdados do Lync Server 2010 não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Lync Server 2013, as políticas e os certificados do XMPP foram configurados, o parceiro federado do XMPP foi configurado no Lync Server 2013



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Para remover a associação de federação herdada de sites do Lync Server 2013

1.  No servidor front-end do Lync Server 2013, abra a topologia existente no construtor de topologias.

2.  No painel esquerdo, navegue até o nó do site, que está localizado diretamente abaixo do **Lync Server**.

3.  Clique com o botão direito no site e depois clique em **Editar propriedades**.

4.  No painel esquerdo, selecione **Rota de federação**.

5.  Em **atribuição de rota de Federação do site**, desmarque a caixa de seleção **habilitar Federação SIP** para desabilitar a rota de Federação através do ambiente herdado Lync Server 2010.
    
    ![Caixa de diálogo Editar propriedades, página rota de Federação](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Caixa de diálogo Editar propriedades, página rota de Federação")

6.  Clique em **OK** para fechar a página Editar Propriedades.

7.  No **Construtor de Topologias**, selecione o nó superior **Lync Server**.

8.  No menu **Ação **, clique em **Publicar topologia**.

9.  Clique em **Avançar** para concluir o processo de publicação e depois clique em **Concluir** quando o processo de publicação estiver completo.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o Servidor de Borda herdado como um Servidor de Borda não federado

1.  No painel esquerdo, navegue para o nó **Lync Server 2010** e depois para o nó **Pools de borda**.

2.  Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.

3.  Selecionar **Geral** no painel esquerdo.

4.  Desmarque a caixa de seleção **Habilitar federação para este pool de Borda (Porta 5061)** e selecione **OK** para fechar a página.
    
    ![Editar propriedades, geral, desmarcar Habilitar Federação](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Editar propriedades, geral, desmarcar Habilitar Federação")

5.  No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.

6.  Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente.

7.  Verifique se a federação do servidor de borda herdado está desativada.
    
    ![Construtor de topologia, pool de borda, Federação desabilitado](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Construtor de topologia, pool de borda, Federação desabilitado")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Para configurar os certificados no Servidor de Borda do Lync Server 2010

1.  Exporte o certificado de proxy de acesso externo, com a chave privada, do servidor de borda do Lync Server 2010 herdado.

2.  No servidor de borda do Lync Server 2013, importe o certificado externo do proxy de acesso da etapa anterior.

3.  Atribua o certificado externo do proxy de acesso à interface externa do Lync Server 2013 do servidor de borda.

4.  O certificado de interface interna do servidor de borda do Lync Server 2013 deve ser solicitado de uma AC confiável e atribuído.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Para alterar a rota de federação do Lync Server 2010 para usar o Servidor de Borda do Lync Server 2013

1.  No Construtor de Topologias, no painel esquerdo, navegue para o nó **Lync Server 2013 ** e depois para o nó **Pools de borda**.

2.  Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.

3.  Selecionar **Geral** no painel esquerdo.

4.  Marque a caixa de seleção **Habilitar federação para este pool de Borda (Porta 5061)** e selecione **OK** para fechar a página.
    
    ![Caixa de diálogo Editar propriedades, página Geral](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")

5.  No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.

6.  Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente.

7.  Verifique se **Federação (porta 5061)** está definida como **Habilitada**.
    
    ![Construtor de topologias, pool de borda, Federação habilitado](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Construtor de topologias, pool de borda, Federação habilitado")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Para atualizar o próximo salto da federação do Servidor de Borda do Lync Server 2013

1.  No Construtor de Topologias, no painel esquerdo, navegue para o nó **Lync Server 2013 ** e depois para o nó **Pools de borda**.

2.  Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**.

3.  Na página **geral** , em **seleção do próximo salto**, selecione na lista suspensa o pool do Lync Server 2013.
    
    ![Caixa de diálogo Editar propriedades, página de próximo salto](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Caixa de diálogo Editar propriedades, página de próximo salto")

4.  Clique em **OK** para fechar a página Editar Propriedades.

5.  No **Construtor de topologias**, selecione o nó superior **Lync Server** .

6.  No menu **Ações**, clique em **Publicar Topologia** e complete o assistente.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Para configurar o caminho de mídia de saída do Servidor de Borda do Lync Server 2013

1.  No construtor de topologias, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o pool abaixo de **servidores front-end Standard Edition** ou **pools de front-ends Enterprise Edition**.

2.  Clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.

3.  Na seção **Associações**, marque a caixa de seleção **Associar pool de Borda (para componentes de mídia)**.
    
    ![Editar propriedades, geral, associar pool de borda](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Editar propriedades, geral, associar pool de borda")

4.  Na caixa suspensa, selecione o servidor de borda do Lync Server 2013.

5.  Clique em **OK** para fechar a página **Editar Propriedades**.

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Para ativar a federação do Servidor de Borda do Lync Server 2013

1.  No Construtor de Topologias, no painel esquerdo, navegue para o nó **Lync Server 2013 ** e depois para o nó **Pools de borda**.

2.  Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**.
    
    <div>
    

    > [!NOTE]  
    > A Federação só pode ser habilitada para um único pool de borda. Se você tiver vários pools de borda, selecione um para usar como o pool de Borda de federação.

    
    </div>

3.  Na página **Geral**, verifique se a configuração **Habilitar federação para este pool de Borda (Porta 5061)** está marcada.
    
    ![Caixa de diálogo Editar propriedades, página Geral](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")

4.  Clique em **OK** para fechar a página Editar Propriedades.

5.  Em seguida, navegue até o nó do site.

6.  Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.

7.  No painel esquerdo, clique em **Rota de federação**.

8.  Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Lync Server 2013 listado.
    
    ![Editar propriedades, página de rota de Federação](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Editar propriedades, página de rota de Federação")

9.  Clique em **OK** para fechar a página **Editar Propriedades**.
    
    Para implantações de múltiplos sites, complete esse procedimento em cada site.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do Servidor de Borda

1.  No **Construtor de topologias**, selecione o nó superior **Lync Server** .

2.  No menu **Ações**, selecione **Publicar Topologia** e conclua o assistente.

3.  Aguarde que a replicação do Active Directory ocorra em todos os pools na implantação.
    
    <div>
    

    > [!NOTE]  
    > Você pode ver a seguinte mensagem:<BR><STRONG>Aviso: a topologia contém mais de um Servidor de Borda Federado. Isso pode ocorrer durante a migração para uma versão superior do produto. Nesse caso, somente um Servidor de Borda seria ativamente usado para federação. Verifique se o registro SRV DNS externo aponta para o Servidor de Borda correto. Se desejar que vários Servidores de Borda de federação permaneçam ativos simultaneamente (isto é, não em um cenário de migração), verifique se todos os parceiros federados estão usando o Lync Server. Verifique se o registro SRV DNS externo lista todos os Servidores de Borda habilitados para federação.</STRONG><BR>Esse aviso é esperado e pode ser ignorado com segurança.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Para configurar o Servidor de Borda do Lync Server 2013

1.  Coloque todos os servidores de borda do Lync Server 2013 online.

2.  Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor de borda do Lync Server 2013, em vez do servidor de borda herdado.
    
    <div>
    

    > [!NOTE]  
    > Se não tiver um balanceador de carga de hardware, será necessário atualizar o registro A de DNS da federação para resolver no novo servidor de borda de acesso do Lync Server. Para obter isso com um mínimo de interrupção, reduza o valor TTL do FQDN de borda de acesso do Lync Server, para que, quando o DNS for atualizado para apontar para a borda de acesso do Lync Server, o acesso de federação e remoto seja atualizado rapidamente.

    
    </div>

3.  Em seguida, pare a **borda de acesso do Lync Server** de cada computador do servidor de borda.

4.  Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.

5.  Na lista de serviços, encontre **Borda de Acesso do Lync Server**.

6.  Clique com o botão direito do mouse no nome dos serviços e selecione **Parar** para parar o serviço.

7.  Defina o tipo de inicialização para **Desativado**.

8.  Clique em **OK** para fechar a janela **Propriedades**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

