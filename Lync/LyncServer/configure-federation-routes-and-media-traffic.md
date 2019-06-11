---
title: Configurar rotas de federação e tráfego de mídia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed16ac6b8aceea6828b600ce18da8b9a72827846
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>Configurar rotas de federação e tráfego de mídia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-15_

A Federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários de organizações separadas se comuniquem entre os limites da rede. Depois de migrar para o pool piloto do Lync Server 2013, você precisará fazer a transição da rota de Federação dos seus servidores do Lync Server 2010 Edge para a rota de Federação do servidor do Lync Server 2013 para servidores de borda.

Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do servidor de borda e do diretor do Lync Server 2010 para o servidor do Lync Server 2013 Edge para uma implantação de um único site.

<div>


> [!IMPORTANT]  
> Alterar a rota de Federação e a rota de tráfego de mídia requer que você agende o tempo de inatividade de manutenção para os servidores Lync Server 2013 e Lync Server 2010 Edge. Esse processo de transição inteiro também significa que o acesso federado estará indisponível para a duração da interrupção. Você deve programar o tempo de inatividade para um horário em que espera a atividade do usuário mínima. Você também deve fornecer uma notificação suficiente para seus usuários finais. Planeje-se adequadamente para esta interrupção e defina as expectativas adequadas dentro da sua organização.



</div>

<div>


> [!IMPORTANT]  
> Se seu servidor de borda herdado do Lync Server 2010 está configurado para usar o mesmo FQDN para o serviço de borda de acesso, serviço de borda de Webconferência e o serviço de borda A/V, os procedimentos desta seção não têm suporte. Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, você deve primeiro migrar todos os usuários do Lync Server 2010 para o Lync Server 2013 e, em seguida, encerrar o servidor de borda do Lync Server 2010 antes de habilitar a Federação no servidor do Lync Server 2013 Edge.



</div>

<div>


> [!IMPORTANT]  
> Se a sua Federação do XMPP for roteada por meio de um servidor de borda do Lync Server 2013, os usuários herdados do Lync Server 2010 não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Lync Server 2013, as políticas e os certificados do XMPP foram configurada, o parceiro federado do XMPP foi configurado no Lync Server 2013 e, por último, as entradas DNS foram atualizadas.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Para remover a associação de Federação herdada dos sites do Lync Server 2013

1.  No servidor de front-end do Lync Server 2013, abra a topologia existente no construtor de topologias.

2.  No painel esquerdo, navegue até o nó do site, localizado diretamente abaixo do **Lync Server**.

3.  Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.

4.  No painel esquerdo, selecione **roteiro de Federação**.

5.  Em **atribuição de rota de Federação do site**, desmarque a caixa de seleção **habilitar Federação SIP** para desabilitar a rota de Federação por meio do ambiente herdado do Lync Server 2010.
    
    ![Caixa de diálogo Editar propriedades, página rota de Federação] (images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Caixa de diálogo Editar propriedades, página rota de Federação")

6.  Clique em **OK** para fechar a página Editar propriedades.

7.  No **Construtor**de topologias, selecione o nó superior do **Lync Server**.

8.  No menu **ação** , clique em **publicar topologia**.

9.  Clique em **Avançar** para concluir o processo de publicação e, em seguida, clique em **concluir** quando o processo de publicação estiver concluído.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o servidor de borda herdado como um servidor de borda não federativo

1.  No painel esquerdo, navegue até o nó do **Lync Server 2010** e, em seguida, para o nó de pools de **borda** .

2.  Clique com o botão direito do mouse no servidor de borda e, em seguida, clique em **Editar propriedades**.

3.  Selecione **geral** no painel esquerdo.

4.  Desmarque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** e selecione **OK** para fechar a página.
    
    ![Editar propriedades, geral, limpar habilitar Federação] (images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Editar propriedades, geral, limpar habilitar Federação")

5.  No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.

6.  Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.

7.  Verifique se a Federação para o servidor de borda herdada está desabilitada.
    
    ![Construtor de topologia, pool de bordas, agrupamento desabilitado] (images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Construtor de topologia, pool de bordas, agrupamento desabilitado")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Para configurar certificados no servidor de borda do Lync Server 2010

1.  Exportar o certificado de proxy de acesso externo, com a chave privada, do servidor de borda do Lync Server 2010 herdado.

2.  No servidor de borda do Lync Server 2013, importe o certificado de proxy externo do Access da etapa anterior.

3.  Atribua o certificado de proxy externo do Access à interface externa do Lync Server 2013 do servidor de borda.

4.  O certificado de interface interna do servidor de borda do Lync Server 2013 deve ser solicitado de uma autoridade de certificação confiável e atribuído.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Para alterar a rota de Federação do Lync Server 2010 para usar o Lync Server 2013 Edge Server

1.  No construtor de topologia, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o nó de pools de **borda** .

2.  Clique com o botão direito do mouse no servidor de borda e, em seguida, clique em **Editar propriedades**.

3.  Selecione **geral** no painel esquerdo.

4.  Marque a entrada da caixa de seleção para **habilitar a Federação para este pool de bordas (porta 5061)** e clique em **OK** para fechar a página.
    
    ![Caixa de diálogo Editar propriedades, página Geral] (images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")

5.  No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.

6.  Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.

7.  Verifique se a **Federação (porta 5061)** está definida como **Enabled**.
    
    ![Construtor de topologia, pool de bordas, agrupamento habilitado] (images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Construtor de topologia, pool de bordas, agrupamento habilitado")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Para atualizar o Lync Server 2013 o próximo nó de Federação do servidor de borda

1.  No construtor de topologia, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o nó de pools de **borda** .

2.  Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**.

3.  Na página **geral** , em **seleção do próximo salto**, selecione na lista suspensa o pool do Lync Server 2013.
    
    ![Caixa de diálogo Editar propriedades, página de próximo salto] (images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Caixa de diálogo Editar propriedades, página de próximo salto")

4.  Clique em **OK** para fechar a página Editar propriedades.

5.  No **Construtor**de topologias, selecione o nó superior do **Lync Server** .

6.  No menu **ação** , clique em **publicar topologia** e conclua o assistente.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Para configurar o caminho da mídia de saída do servidor de borda do Lync Server 2013

1.  No construtor de topologia, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o pool abaixo de **servidores front-end da edição padrão** ou **pools front-ends do Enterprise Edition**.

2.  Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.

3.  Na seção **associações** , marque a caixa de seleção **associar o pool de bordas (para componentes de mídia)** .
    
    ![Editar propriedades, geral, associar pool de bordas] (images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Editar propriedades, geral, associar pool de bordas")

4.  Na caixa suspensa, selecione o servidor de borda do Lync Server 2013.

5.  Clique em **OK** para fechar a página **Editar propriedades** .

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Para ativar a Federação do servidor de borda do Lync Server 2013

1.  No construtor de topologia, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o nó de pools de **borda** .

2.  Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**.
    
    <div>
    

    > [!NOTE]  
    > A Federação só pode ser habilitada para um único pool de bordas. Se você tiver vários pools de bordas, selecione um para usá-lo como o pool de bordas de Federação.

    
    </div>

3.  Na página **geral** , verifique se a configuração **habilitar Federação para este pool de bordas (porta 5061)** está marcada.
    
    ![Caixa de diálogo Editar propriedades, página Geral] (images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")

4.  Clique em **OK** para fechar a página Editar propriedades.

5.  Em seguida, navegue até o nó do site.

6.  Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.

7.  No painel esquerdo, clique em **rota de Federação**.

8.  Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Lync Server 2013 listado.
    
    ![Editar propriedades, página de roteiro de Federação] (images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Editar propriedades, página de roteiro de Federação")

9.  Clique em **OK** para fechar a página **Editar propriedades** .
    
    Para implantações em vários locais, conclua este procedimento em cada site.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do servidor de borda

1.  No **Construtor**de topologias, selecione o nó superior do **Lync Server** .

2.  No menu **ação** , selecione **publicar topologia** e conclua o assistente.

3.  Aguarde até que a replicação do Active Directory ocorra em todos os pools da implantação.
    
    <div>
    

    > [!NOTE]  
    > Você pode ver a seguinte mensagem:<BR><STRONG>Aviso: a topologia contém mais de um servidor de borda federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um servidor de borda seria usado ativamente para Federação. Verifique se o registro SRV DNS externo aponta para o servidor de borda correto. Se você quiser implantar várias bordas de servidor de borda para ativar simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Lync Server. Verifique se o registro SRV DNS externo lista todos os servidores de borda habilitados para Federação.</STRONG><BR>Este aviso é esperado e pode ser ignorado com segurança.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Para configurar o servidor de borda do Lync Server 2013

1.  Reúna todos os servidores do Lync Server 2013 Edge online.

2.  Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor do Lync 2013, em vez do servidor de borda herdado.
    
    <div>
    

    > [!NOTE]  
    > Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS a para que a Federação seja resolvida para o novo servidor de borda de acesso do Lync Server. Para fazer isso com o mínimo de interrupção, reduza o valor TLL do FQDN do servidor de borda de acesso externo do Lync Server, para que, quando o DNS for atualizado, aponte para a nova borda de acesso do Lync Server, a Federação e o acesso remoto sejam atualizados rapidamente.

    
    </div>

3.  Em seguida, interrompa a **borda de acesso do Lync Server** de cada computador do servidor de borda.

4.  Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.

5.  Na lista serviços, localize a **borda de acesso do Lync Server**.

6.  Clique com o botão direito do mouse no nome dos serviços e, em seguida, selecione **parar** para interromper o serviço.

7.  Defina o tipo de inicialização **** como desabilitado.

8.  Clique em **OK** para fechar a janela **Propriedades** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

