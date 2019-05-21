---
title: Configurar rotas de federação e tráfego de mídia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: A Federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários de organizações separadas se comuniquem entre os limites da rede. Depois de migrar para o pool piloto, você precisa fazer a transição da rota de Federação de seus servidores de borda de versões anteriores para a rota de Federação dos seus servidores de borda do Skype for Business Server 2019.
ms.openlocfilehash: 6b76932c8b988dbed61cba1470f32a51f6585536
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298316"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar rotas de federação e tráfego de mídia

A Federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários de organizações separadas se comuniquem entre os limites da rede. Depois de migrar para o pool piloto, você precisará fazer a transição da rota de Federação dos servidores de borda da versão anterior para a rota de Federação dos seus servidores de borda do Skype for Business Server 2019.
  
Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do servidor de borda e do diretor da sua versão anterior para o seu servidor de borda do Skype for Business Server 2019 para uma implantação de um único site.
  
> [!IMPORTANT]
> Alterar a rota de Federação e a rota de tráfego de mídia requer que você agende o tempo de inatividade de manutenção para os servidores do Skype for Business Server 2019 e do Edge versão anterior. Esse processo de transição inteiro também significa que o acesso federado estará indisponível para a duração da interrupção. Você deve programar o tempo de inatividade para um horário em que espera a atividade do usuário mínima. Você também deve fornecer uma notificação suficiente para seus usuários finais. Planeje-se adequadamente para esta interrupção e defina as expectativas adequadas dentro da sua organização. 
  
> [!IMPORTANT]
> Se o servidor de borda herdado estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda a/V, os procedimentos desta seção não serão suportados. Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, primeiro você deve migrar todos os seus usuários e, em seguida, encerrar o servidor de borda de versões anteriores antes de habilitar a Federação no servidor de borda do Skype for Business Server 2019. 
  
> [!IMPORTANT]
> Se a sua Federação do XMPP for roteada por meio de um servidor de borda do Skype for Business Server 2019, os usuários na versão anterior não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Skype for Business Server 2019, políticas do XMPP e os certificados foram configurados, o parceiro federado do XMPP foi configurado no Skype for Business Server 2019 e, finalmente, as entradas DNS foram atualizadas. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para remover a associação de Federação herdada dos sites do Skype for Business Server 2019

1. No servidor front-end do Skype for Business Server 2019, abra a topologia existente no construtor de topologias. 
    
2. No painel esquerdo, navegue até o nó do site, localizado diretamente abaixo **do Skype for Business Server**.
    
3. Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.
    
4. No painel esquerdo, selecione **roteiro de Federação**. 
    
5. Em **atribuição de rota de Federação do site**, desmarque a caixa de seleção **habilitar Federação SIP** para desabilitar a rota de Federação por meio do ambiente herdado. 
  
6. Clique em **OK** para fechar a página Editar propriedades. 
    
7. No **Construtor**de topologias, selecione o nó superior **Skype for Business Server**.
    
8. No menu **ação** , clique em **publicar topologia**.
    
9. Clique em **Avançar** para concluir o processo de publicação e, em seguida, clique em **concluir** quando o processo de publicação estiver concluído. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o servidor de borda herdado como um servidor de borda não federativo

1. No painel esquerdo, navegue até o nó instalação herdada e, em seguida, para o nó pools de **borda** . 
    
2. Clique com o botão direito do mouse no servidor de borda e, em seguida, clique em **Editar propriedades**.
    
3. Selecione **geral** no painel esquerdo. 
    
4. Desmarque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** e selecione **OK** para fechar a página. 
  
5. No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.
    
6. Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente. 
    
7. Verifique se a Federação do servidor de borda herdada está desabilitada no construtor de topologias.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados no servidor de borda herdado

1. Exportar o certificado de proxy de acesso externo, com a chave privada, do servidor de borda herdado. 
    
2. No servidor de borda do Skype for Business Server 2019 e importar o certificado externo de proxy do Access da etapa anterior.
    
3. Atribua o certificado de proxy externo do Access à interface externa do Skype for Business Server 2019 do servidor de borda.
    
4. O certificado de interface interna do servidor de borda do Skype for Business Server 2019 deve ser solicitado de uma autoridade de certificação confiável e atribuído. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para alterar a rota de Federação da versão anterior para usar o servidor de borda do Skype for Business Server 2019

1. No construtor de topologia, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó de pools de **borda** . 
    
2. Clique com o botão direito do mouse no servidor de borda e, em seguida, clique em **Editar propriedades**.
    
3. Selecione **geral** no painel esquerdo. 
    
4. Marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** e, em seguida, clique em **OK** para fechar a página. 
  
5. No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.
    
6. Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente. 
    
7. Verifique se a **Federação (porta 5061)** está definida como **Enabled** no construtor de topologias.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para atualizar o Skype for Business Server 2019 o próximo nó de Federação do servidor de borda

1. No construtor de topologia, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó de pools de **borda** . 
    
2. Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**. 
    
3. Na página **geral** , em **seleção do próximo salto**, selecione na lista suspensa o pool do Skype for Business Server 2019.
  
4. Clique em **OK** para fechar a página Editar propriedades. 
    
5. No **Construtor**de topologias, selecione o nó superior **Skype for Business Server**. 
    
6. No menu **ação** , clique em **publicar topologia** e conclua o assistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar o caminho da mídia de saída do servidor de borda do Skype for Business Server 2019

1. No construtor de topologia, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o pool abaixo de **servidores front-end da edição padrão** ou **pools front-ends do Enterprise Edition**.
    
2. Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.
    
3. Na seção **associações** , marque a caixa de seleção **associar o pool de bordas (para componentes de mídia)** . 
  
4. Na caixa suspensa, selecione o servidor de borda do Skype for Business Server 2019.
    
5. Clique em **OK** para fechar a página **Editar propriedades** . 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para ativar a Federação do servidor de borda do Skype for Business Server 2019

1. No construtor de topologia, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó de pools de **borda** . 
    
2. Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**. 
    
    > [!NOTE]
    > A Federação só pode ser habilitada para um único pool de bordas. Se você tiver vários pools de bordas, selecione um para usá-lo como o pool de bordas de Federação. 
  
3. Na página **geral** , verifique se a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** está marcada. 
  
4. Clique em **OK** para fechar a página Editar propriedades. 
    
5. Navegue até o nó do site. 
    
6. Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.
    
7. No painel esquerdo, clique em **rota de Federação**.
    
8. Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Skype for Business Server 2019 listado. 
  
9. Clique em **OK** para fechar a página **Editar propriedades** . 
    
     Para implantações em vários locais, conclua este procedimento em cada site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do servidor de borda

1. No **Construtor**de topologias, selecione o nó superior **Skype for Business Server**. 
    
2. No menu **ação** , selecione **publicar topologia** e conclua o assistente. 
    
3. Aguarde até que a replicação do Active Directory ocorra em todos os pools da implantação.
    
    > [!NOTE]
    > Você pode ver a seguinte mensagem: **AVISO: a topologia contém mais de um servidor de borda federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um servidor de borda seria usado ativamente para Federação. Verifique se o registro SRV DNS externo aponta para o servidor de borda correto. Se você quiser implantar várias bordas de servidor de borda para ativar simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Skype for Business Server. Verifique se o registro SRV DNS externo lista todos os servidores de borda habilitados para Federação.** Este aviso é esperado e pode ser ignorado com segurança. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar o servidor de borda do Skype for Business Server 2019

1. Reúna todos os servidores de borda do Skype for Business Server 2019 online. 
    
2. Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) ao Skype for Business Server 2019 Edge Server, em vez do servidor de borda herdado.
    
    > [!NOTE]
    > Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS a para que a Federação seja resolvida para o novo servidor de borda de acesso do Skype for Business Server. Para fazer isso com o mínimo de interrupções, reduza o valor de TLL para o FQDN externo de borda de acesso do Skype for Business Server, de forma que, quando o DNS for atualizado para apontar para a nova borda de acesso do Skype for Business Server, a Federação e o acesso remoto serão atualizados rapidamente. 
  
3. Pare a **borda de acesso do Skype for Business Server** de cada computador do servidor de borda. 
    
4. Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.
    
5. Na lista serviços, localize **borda de acesso do Skype for Business Server**.
    
6. Clique com o botão direito do mouse no nome dos serviços e, em seguida, selecione **parar** para interromper o serviço. 
    
7. Defina o tipo de inicialização **** como desabilitado. 
    
8. Clique em **OK** para fechar a janela **Propriedades** . 
    

