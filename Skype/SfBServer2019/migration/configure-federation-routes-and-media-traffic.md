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
description: A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Depois de migrar para o pool piloto, você precisará fazer a transição da rota de federação dos Servidores de Borda de versões anteriores para a rota de federação dos Servidores de Borda do Skype for Business Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754031"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configure o tráfego de mídia e rotas de federação

A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Depois de migrar para o pool piloto, você precisará fazer a transição da rota de federação dos Servidores de Borda da versão anterior para a rota de federação dos Servidores de Borda do Skype for Business Server 2019.
  
Use os procedimentos a seguir para fazer a transição da rota de federação e da rota de tráfego de mídia do Servidor de Borda e diretor da versão anterior para o Servidor de Borda do Skype for Business Server 2019, para uma implantação de site único.
  
> [!IMPORTANT]
> Alterar a rota de federação e a rota de tráfego de mídia exige que você agende o tempo de inatividade de manutenção para o Skype for Business Server 2019 e os Servidores de Borda da versão anterior. Todo esse processo de transição também significa que o acesso federado não estará disponível durante a interrupção. Agende o tempo de inatividade para um período no qual você espera o mínimo de atividade de usuário. Você também deve fornecer notificações suficientes para seus usuários finais. Planeje-se adequadamente para essa interrupção e defina as expectativas apropriadas dentro de sua organização. 
  
> [!IMPORTANT]
> Se seu Servidor de Borda herdado estiver configurado para usar o mesmo FQDN para o serviço de Borda de Acesso, o serviço de Borda de Webconferência e o serviço de Borda A/V, os procedimentos nesta seção não serão suportados. Se os serviços de Borda herdados estão configurados para usar o mesmo FQDN, primeiro você deve migrar todos os usuários e, em seguida, descomissionar o Servidor de Borda de versões anteriores antes de habilitar a federação no Servidor de Borda do Skype for Business Server 2019. 
  
> [!IMPORTANT]
> Se sua federação XMPP for roteada através de um Servidor de Borda do Skype for Business Server 2019, os usuários na versão anterior não poderão se comunicar com o parceiro federado XMPP até que todos os usuários tenham sido movidos para o Skype for Business Server 2019, as políticas E certificados XMPP tenham sido configurados, o parceiro federado XMPP foi configurado no Skype for Business Server 2019 e, por fim, as entradas DNS foram atualizadas. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para remover a associação de federação herdada dos sites do Skype for Business Server 2019

1. No servidor front-end do Skype for Business Server 2019, abra a topologia existente no Construtor de Topologias. 
    
2. No painel esquerdo, navegue até o nó do site, que está localizado diretamente **abaixo do Skype for Business Server.**
    
3. Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.
    
4. No painel esquerdo, selecione **Rota de federação**. 
    
5. Em **Atribuição da rota de federação do site,** **des** clear the Enable SIP federation check box to disable the federation route through the legacy environment. 
  
6. Clique em **OK** para fechar a página Editar Propriedades. 
    
7. No **Construtor de Topologias,** selecione o nó **superior do Skype for Business Server.**
    
8. No menu **Ação**, clique em **Publicar topologia**.
    
9. Clique **em Próximo** para concluir o processo de publicação e clique em **Concluir** quando o processo de publicação for concluído. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o Servidor de Borda herdado como um Servidor de Borda não federado

1. No painel esquerdo, navegue até o nó de instalação herddo e, em seguida, para o **nó pools de** Borda. 
    
2. Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.
    
3. Selecionar **Geral** no painel esquerdo. 
    
4. Des limpe a caixa de seleção Habilitar federação para este pool de Borda **(porta 5061)** e selecione **OK** para fechar a página. 
  
5. No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.
    
6. Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente. 
    
7. Verifique se a federação para o servidor de Borda herdado está desabilitada no Construtor de Topologias.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados no Servidor de Borda herddo

1. Exporte o certificado de Proxy de Acesso externo, com a chave privada, do Servidor de Borda herdado. 
    
2. No Servidor de Borda do Skype for Business Server 2019 e importe o certificado externo do Proxy de Acesso da etapa anterior.
    
3. Atribua o certificado externo do Proxy de Acesso à interface externa do Skype for Business Server 2019 do Servidor de Borda.
    
4. O certificado de interface interna do Servidor de Borda do Skype for Business Server 2019 deve ser solicitado a uma CA confiável e atribuído. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para alterar a rota de federação da versão anterior para usar o Servidor de Borda do Skype for Business Server 2019

1. No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, para o nó **pools de** Borda. 
    
2. Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.
    
3. Selecionar **Geral** no painel esquerdo. 
    
4. Marque a caixa de seleção Habilitar federação para este pool de Borda **(porta 5061)** e clique em **OK** para fechar a página. 
  
5. No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.
    
6. Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente. 
    
7. Verifique se **a Federação (porta 5061)** está definida **como Habilitada** no Construtor de Topologias.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para atualizar o próximo salto da federação do Servidor de Borda do Skype for Business Server 2019

1. No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, para o nó **pools de** Borda. 
    
2. Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**. 
    
3. Na página **Geral,** em **Seleção** de Próximo salto, selecione na lista drop-down o pool do Skype for Business Server 2019.
  
4. Clique em **OK** para fechar a página Editar Propriedades. 
    
5. No **Construtor de Topologias,** selecione o nó **superior do Skype for Business Server.** 
    
6. No menu **Ações**, clique em **Publicar topologia** e complete o assistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar o caminho de mídia de saída do Servidor de Borda do Skype for Business Server 2019

1. No Construtor de Topologias, no painel esquerdo, navegue até o nó **skype for Business Server 2019** e, em seguida, para o pool abaixo servidores de **front-end Standard Edition** ou pools de **front-end Enterprise Edition**.
    
2. Clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.
    
3. Na seção **Associações**, marque a caixa de seleção **Associar pool de Borda (para componentes de mídia)**. 
  
4. Na caixa de lista, selecione o Servidor de Borda do Skype for Business Server 2019.
    
5. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para ativar a federação do Servidor de Borda do Skype for Business Server 2019

1. No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, para o nó **pools de** Borda. 
    
2. Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**. 
    
    > [!NOTE]
    > A federação só pode ser habilitada para um único pool de Borda. Se você tiver vários pools de borda, selecione um para usar como o pool de Borda de federação. 
  
3. Na página **Geral,** verifique se a caixa de seleção Habilitar federação para este pool de Borda **(Porta 5061)** está marcada. 
  
4. Clique em **OK** para fechar a página Editar Propriedades. 
    
5. Navegue até o nó do site. 
    
6. Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.
    
7. No painel esquerdo, clique em **Rota de federação**.
    
8. Em **Atribuição da** rota de federação do site, selecione Habilitar federação **SIP** e, na lista, selecione o Servidor de Borda do Skype for Business Server 2019 listado. 
  
9. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
     Para implantações de múltiplos sites, complete esse procedimento em cada site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do Servidor de Borda

1. No **Construtor de Topologias,** selecione o nó **superior do Skype for Business Server.** 
    
2. No menu **Ações**, selecione **Publicar Topologia** e conclua o assistente. 
    
3. Aguarde que a replicação do Active Directory ocorra em todos os pools na implantação.
    
    > [!NOTE]
    > Você pode ver a seguinte mensagem: **Aviso: A topologia contém mais de um Servidor de Borda Federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um Servidor de Borda seria usado ativamente para federação. Verifique se o registro SRV de DNS externo aponta para o Servidor de Borda correto. Se você quiser implantar vários Servidores de Borda de federação para estar ativo simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Skype for Business Server. Verifique se o registro SRV de DNS externo lista todos os Servidores de Borda habilitados para federação.** Esse aviso é esperado e pode ser ignorado com segurança. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar o Servidor de Borda do Skype for Business Server 2019

1. Colocar todos os Servidores de Borda do Skype for Business Server 2019 online. 
    
2. Atualize as regras de roteamento de firewall externo ou as configurações do balanceador de carga de hardware para enviar tráfego SIP para acesso externo (normalmente porta 443) e federação (normalmente a porta 5061) para o Servidor de Borda do Skype for Business Server 2019, em vez do Servidor de Borda herdado.
    
    > [!NOTE]
    > Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS A para que a federação seja resolvida para o novo servidor de Borda de Acesso do Skype for Business Server. Para fazer isso com o mínimo de interrupção, reduza o valor de TLL para o FQDN externo da Borda de Acesso do Skype for Business Server para que, quando o DNS for atualizado para apontar para a nova Borda de Acesso do Skype for Business Server, a federação e o acesso remoto sejam atualizados rapidamente. 
  
3. Pare a **Borda de Acesso do Skype for Business Server** de cada computador servidor de borda. 
    
4. Em cada computador servidor de borda herddo, abra **o** applet serviços das **Ferramentas Administrativas**.
    
5. Na lista de serviços, encontre a **Borda de Acesso do Skype for Business Server.**
    
6. Clique com o botão direito do mouse no nome dos serviços e selecione **Parar** para parar o serviço. 
    
7. Defina o tipo de inicialização para **Desativado**. 
    
8. Clique em **OK** para fechar a janela **Propriedades**. 
    

