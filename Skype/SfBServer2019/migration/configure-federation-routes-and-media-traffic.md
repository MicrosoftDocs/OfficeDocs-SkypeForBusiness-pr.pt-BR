---
title: Configure o tráfego de mídia e rotas de federação
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Após migrar para o pool piloto, você precisará fazer a transição da rota de Federação de seus servidores de borda de versões anteriores para a rota de Federação de seus servidores de borda do Skype for Business Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754031"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configure o tráfego de mídia e rotas de federação

A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Após migrar para o pool piloto, você precisará fazer a transição da rota de Federação dos servidores de borda da versão anterior para a rota de Federação de seus servidores de borda do Skype for Business Server 2019.
  
Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do diretor e servidor de borda da versão anterior para o servidor de borda do Skype for Business Server 2019, para uma implantação de site único.
  
> [!IMPORTANT]
> Alterar a rota de Federação e a rota de tráfego de mídia exige que você agende o tempo de inatividade de manutenção para o Skype for Business Server 2019 e para os servidores de borda de versão anterior. Todo esse processo de transição também significa que o acesso federado não estará disponível durante a interrupção. Agende o tempo de inatividade para um período no qual você espera o mínimo de atividade de usuário. Você também deve fornecer notificações suficientes para seus usuários finais. Planeje-se adequadamente para essa interrupção e defina as expectativas apropriadas dentro de sua organização. 
  
> [!IMPORTANT]
> Se o servidor de borda herdado estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda A/V, não haverá suporte para os procedimentos desta seção. Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, você deverá primeiro migrar todos os seus usuários e, em seguida, encerrar o servidor de borda de versões anteriores antes de habilitar a Federação no servidor de borda do Skype for Business Server 2019. 
  
> [!IMPORTANT]
> Se sua Federação do XMPP for encaminhada por um servidor de borda do Skype for Business Server 2019, os usuários da versão anterior não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Skype for Business Server 2019, as políticas e os certificados do XMPP tenham sido configurados, o parceiro federado do XMPP tenha sido configurado no Skype for Business Server 2019 e, por fim, as entradas DNS foram atualizadas. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para remover a associação de Federação herdada dos sites do Skype for Business Server 2019

1. No servidor front-end do Skype for Business Server 2019, abra a topologia existente no construtor de topologias. 
    
2. No painel esquerdo, navegue até o nó do site, que está localizado diretamente abaixo **do Skype for Business Server**.
    
3. Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.
    
4. No painel esquerdo, selecione **Rota de federação**. 
    
5. Em **atribuição de rota de Federação do site**, desmarque a caixa de seleção **habilitar Federação SIP** para desabilitar a rota de Federação pelo ambiente herdado. 
  
6. Clique em **OK** para fechar a página Editar Propriedades. 
    
7. No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**.
    
8. No menu **Ação **, clique em **Publicar topologia**.
    
9. Clique em **Avançar** para concluir o processo de publicação e, em seguida, clique em **concluir** quando o processo de publicação for concluído. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o Servidor de Borda herdado como um Servidor de Borda não federado

1. No painel esquerdo, navegue até o nó de instalação herdado e, em seguida, para o nó **pools de borda** . 
    
2. Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.
    
3. Selecionar **Geral** no painel esquerdo. 
    
4. Desmarque a caixa de seleção **habilitar Federação para este pool de borda (porta 5061)** e selecione **OK** para fechar a página. 
  
5. No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.
    
6. Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente. 
    
7. Verifique se a Federação do servidor de borda herdado está desabilitada no construtor de topologias.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados no servidor de borda herdado

1. Exporte o certificado de proxy de acesso externo, com a chave privada, do servidor de borda herdado. 
    
2. No servidor de borda do Skype for Business Server 2019 e importe o certificado externo do proxy de acesso da etapa anterior.
    
3. Atribua o certificado externo do proxy de acesso à interface externa do Skype for Business Server 2019 do servidor de borda.
    
4. O certificado de interface interna do servidor de borda do Skype for Business Server 2019 deve ser solicitado de uma AC confiável e atribuído. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para alterar a rota de Federação da versão anterior para usar o servidor de borda do Skype for Business Server 2019

1. No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó **pools de borda** . 
    
2. Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.
    
3. Selecionar **Geral** no painel esquerdo. 
    
4. Marque a caixa de seleção **habilitar Federação para este pool de borda (porta 5061)** e clique em **OK** para fechar a página. 
  
5. No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.
    
6. Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente. 
    
7. Verifique se **Federation (porta 5061)** está definido como **habilitado** no construtor de topologias.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para atualizar o próximo salto de Federação do servidor de borda do Skype for Business Server 2019

1. No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó **pools de borda** . 
    
2. Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**. 
    
3. Na página **geral** , em **seleção do próximo salto**, selecione na lista suspensa o pool do Skype for Business Server 2019.
  
4. Clique em **OK** para fechar a página Editar Propriedades. 
    
5. No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**. 
    
6. No menu **Ações**, clique em **Publicar topologia** e complete o assistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar o caminho de mídia de saída do servidor de borda do Skype for Business Server 2019

1. No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o pool abaixo de **servidores front-end Standard Edition** ou **pools de front-ends Enterprise Edition**.
    
2. Clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.
    
3. Na seção **Associações**, marque a caixa de seleção **Associar pool de Borda (para componentes de mídia)**. 
  
4. Na caixa suspensa, selecione o servidor de borda do Skype for Business Server 2019.
    
5. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para ativar a Federação do servidor de borda do Skype for Business Server 2019

1. No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó **pools de borda** . 
    
2. Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**. 
    
    > [!NOTE]
    > A Federação só pode ser habilitada para um único pool de borda. Se você tiver vários pools de borda, selecione um para usar como o pool de Borda de federação. 
  
3. Na página **geral** , verifique se a caixa de seleção **habilitar Federação para este pool de borda (porta 5061)** está marcada. 
  
4. Clique em **OK** para fechar a página Editar Propriedades. 
    
5. Navegue até o nó do site. 
    
6. Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.
    
7. No painel esquerdo, clique em **Rota de federação**.
    
8. Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Skype for Business Server 2019 listado. 
  
9. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
     Para implantações de múltiplos sites, complete esse procedimento em cada site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do Servidor de Borda

1. No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**. 
    
2. No menu **Ações**, selecione **Publicar Topologia** e conclua o assistente. 
    
3. Aguarde que a replicação do Active Directory ocorra em todos os pools na implantação.
    
    > [!NOTE]
    > Você pode ver a seguinte mensagem: **AVISO: a topologia contém mais de um servidor de borda federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, somente um servidor de borda seria usado ativamente para Federação. Verifique se o registro SRV de DNS externo aponta para o servidor de borda correto. Se você deseja implantar vários servidores de borda de Federação para que fiquem ativos simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Skype for Business Server. Verifique se o registro SRV DNS externo lista todos os servidores de borda habilitados para Federação.** Esse aviso é esperado e pode ser ignorado com segurança. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar o servidor de borda do Skype for Business Server 2019

1. Traga todos os servidores de borda do Skype for Business Server 2019 online. 
    
2. Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor de borda do Skype for Business Server 2019, em vez do servidor de borda herdado.
    
    > [!NOTE]
    > Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro a de DNS para que a Federação seja resolvida para o novo servidor de borda de acesso do Skype for Business Server. Para fazer isso com o mínimo de interrupção, reduza o valor de TLL para o FQDN externo de borda de acesso do Skype for Business Server, para que, quando o DNS for atualizado para apontar para a nova borda de acesso do Skype for Business Server, a Federação e o acesso remoto sejam atualizados rapidamente. 
  
3. Interrompa a **borda de acesso do Skype for Business Server** de cada computador do servidor de borda. 
    
4. Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.
    
5. Na lista serviços, encontre **borda de acesso do Skype for Business Server**.
    
6. Clique com o botão direito do mouse no nome dos serviços e selecione **Parar** para parar o serviço. 
    
7. Defina o tipo de inicialização para **Desativado**. 
    
8. Clique em **OK** para fechar a janela **Propriedades**. 
    

