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
ms.localizationpriority: medium
description: A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Depois de migrar para o pool piloto, você precisa fazer a transição da rota de federação dos Servidores de Borda das versões anteriores para a rota de federação dos servidores de borda Skype for Business Server 2019.
ms.openlocfilehash: f051321667e12a468df1186147f6fab1d7bbe5cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613400"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configure o tráfego de mídia e rotas de federação

A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Depois de migrar para o pool piloto, você precisa fazer a transição da rota de federação dos Servidores de Borda da versão anterior para a rota de federação dos servidores de borda Skype for Business Server 2019.
  
Use os procedimentos a seguir para fazer a transição da rota de federação e a rota de tráfego de mídia do Servidor de Borda e Diretor da versão anterior para o Servidor de Borda Skype for Business Server 2019, para uma implantação de site único.
  
> [!IMPORTANT]
> Alterar a rota de federação e a rota de tráfego de mídia exige que você agende o tempo de inatividade de manutenção para o Skype for Business Server 2019 e servidores de Borda da versão anterior. Todo esse processo de transição também significa que o acesso federado não estará disponível durante a interrupção. Agende o tempo de inatividade para um período no qual você espera o mínimo de atividade de usuário. Você também deve fornecer notificações suficientes para seus usuários finais. Planeje-se adequadamente para essa interrupção e defina as expectativas apropriadas dentro de sua organização. 
  
> [!IMPORTANT]
> Se o Servidor de Borda herdado estiver configurado para usar o mesmo FQDN para o serviço de Borda de Acesso, serviço de Borda de WebConferência e o serviço de Borda A/V, os procedimentos nesta seção não são suportados. Se os serviços de Borda herdados estão configurados para usar o mesmo FQDN, primeiro você deve migrar todos os usuários e, em seguida, desmantelar as versões anteriores do Servidor de Borda antes de habilitar a federação no Servidor de Borda Skype for Business Server 2019. 
  
> [!IMPORTANT]
> Se sua federação XMPP for roteada por meio de um Servidor de Borda do Skype for Business Server 2019, os usuários da versão anterior não poderão se comunicar com o parceiro federado XMPP até que todos os usuários tenham sido movidos para o Skype for Business Server 2019, as políticas e certificados XMPP foram configurados, o parceiro federado XMPP foi configurado no Skype for Business Server 2019 e, por fim, as entradas DNS foram atualizadas. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para remover a associação de federação herdado de sites Skype for Business Server 2019

1. No servidor Skype for Business Server front-end 2019, abra a topologia existente no Construtor de Topologias. 
    
2. No painel esquerdo, navegue até o nó do site, que está localizado diretamente abaixo **Skype for Business Server**.
    
3. Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.
    
4. No painel esquerdo, selecione **Rota de federação**. 
    
5. Em **Atribuição de rota de federação de site**, desembolse a caixa de seleção **Habilitar** federação SIP para desabilitar a rota de federação pelo ambiente herdado. 
  
6. Clique em **OK** para fechar a página Editar Propriedades. 
    
7. No **Construtor de Topologias,** selecione o nó **superior Skype for Business Server**.
    
8. No menu **Ação**, clique em **Publicar topologia**.
    
9. Clique **em Próximo** para concluir o processo de publicação e clique em **Concluir** quando o processo de publicação for concluído. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o Servidor de Borda herdado como um Servidor de Borda não federado

1. No painel esquerdo, navegue até o nó de instalação herdável e, em seguida, para o **nó Pools de** Borda. 
    
2. Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.
    
3. Selecionar **Geral** no painel esquerdo. 
    
4. Desembolse a caixa de seleção Habilitar federação para este pool de Borda **(porta 5061)** e selecione **OK** para fechar a página. 
  
5. No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.
    
6. Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente. 
    
7. Verifique se a federação do servidor de Borda herdado está desabilitada no Construtor de Topologias.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados no Servidor de Borda herddo

1. Exporte o certificado proxy de acesso externo, com a chave privada, do Servidor de Borda herdado. 
    
2. No servidor de borda Skype for Business Server 2019 e importe o certificado externo do Proxy de Acesso da etapa anterior.
    
3. Atribua o certificado externo proxy de acesso à interface externa Skype for Business Server 2019 do Servidor de Borda.
    
4. O certificado de interface interna do servidor de borda Skype for Business Server 2019 deve ser solicitado de uma CA confiável e atribuído. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para alterar a rota de federação da versão anterior para usar Skype for Business Server Servidor de Borda 2019

1. No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, até o nó **Pools de** Borda. 
    
2. Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.
    
3. Selecionar **Geral** no painel esquerdo. 
    
4. Marque a caixa de seleção Habilitar federação para este pool de **Borda (porta 5061)** e clique em **OK** para fechar a página. 
  
5. No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.
    
6. Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente. 
    
7. Verifique se **Federação (porta 5061)** está definida como **Habilitado no** Construtor de Topologias.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para atualizar Skype for Business Server próximo salto da federação do Servidor de Borda 2019

1. No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, até o nó **Pools de** Borda. 
    
2. Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**. 
    
3. Na página **Geral,** em **Seleção de Próximo salto**, selecione na lista lista Skype for Business Server 2019.
  
4. Clique em **OK** para fechar a página Editar Propriedades. 
    
5. No **Construtor de Topologias,** selecione o nó **superior Skype for Business Server**. 
    
6. No menu **Ações**, clique em **Publicar topologia** e complete o assistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar Skype for Business Server de mídia de saída do Servidor de Borda 2019

1. No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, para o pool abaixo Edição Standard Servidores **Front-End** ou **pools de front-end Edição Enterprise**.
    
2. Clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.
    
3. Na seção **Associações**, marque a caixa de seleção **Associar pool de Borda (para componentes de mídia)**. 
  
4. Na caixa de seleção, selecione o servidor de borda Skype for Business Server 2019.
    
5. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para ativar a federação Skype for Business Server Servidor de Borda 2019

1. No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, até o nó **Pools de** Borda. 
    
2. Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**. 
    
    > [!NOTE]
    > A federação só pode ser habilitada para um único pool de Borda. Se você tiver vários pools de borda, selecione um para usar como o pool de Borda de federação. 
  
3. Na página **Geral,** verifique se a caixa de seleção Habilitar federação para este pool de **Borda (Porta 5061)** está selecionada. 
  
4. Clique em **OK** para fechar a página Editar Propriedades. 
    
5. Navegue até o nó do site. 
    
6. Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.
    
7. No painel esquerdo, clique em **Rota de federação**.
    
8. Em **Atribuição de rota de** federação de site, selecione **Habilitar** federação SIP e, na lista, selecione o servidor de borda Skype for Business Server 2019 listado. 
  
9. Clique em **OK** para fechar a página **Editar Propriedades**. 
    
     Para implantações de múltiplos sites, complete esse procedimento em cada site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do Servidor de Borda

1. No **Construtor de Topologias,** selecione o nó **superior Skype for Business Server**. 
    
2. No menu **Ações**, selecione **Publicar Topologia** e conclua o assistente. 
    
3. Aguarde que a replicação do Active Directory ocorra em todos os pools na implantação.
    
    > [!NOTE]
    > Você pode ver a seguinte mensagem: **Aviso: A topologia contém mais de um Servidor de Borda Federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um Servidor de Borda seria usado ativamente para federação. Verifique se o registro SRV DNS externo aponta para o Servidor de Borda correto. Se você deseja implantar vários Servidores de Borda de federação para estar ativo simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando Skype for Business Server. Verifique se o registro SRV DNS externo lista todos os Servidores de Borda habilitados para federação.** Esse aviso é esperado e pode ser ignorado com segurança. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar Skype for Business Server Servidor de Borda 2019

1. Traga todos os servidores de borda Skype for Business Server 2019 online. 
    
2. Atualize as regras de roteamento de firewall externo ou as configurações do balanceador de carga de hardware para enviar tráfego SIP para acesso externo (geralmente porta 443) e federação (normalmente porta 5061) para o Servidor de Borda do Skype for Business Server 2019, em vez do Servidor de Borda herdado.
    
    > [!NOTE]
    > Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS A para federação para resolver para o novo servidor de Borda de Skype for Business Server Access. Para fazer isso com o mínimo de interrupção, reduza o valor de TLL para o FQDN de Borda de Acesso externo Skype for Business Server para que, quando o DNS for atualizado para apontar para a nova Borda de Acesso Skype for Business Server, a federação e o acesso remoto serão atualizados rapidamente. 
  
3. Pare o **Skype for Business Server de Acesso** de cada computador do Servidor de Borda. 
    
4. Em cada computador servidor de borda herddo, abra o applet **Serviços** a partir das **Ferramentas Administrativas**.
    
5. Na lista de serviços, encontre **Skype for Business Server Borda de Acesso**.
    
6. Clique com o botão direito do mouse no nome dos serviços e selecione **Parar** para parar o serviço. 
    
7. Defina o tipo de inicialização para **Desativado**. 
    
8. Clique em **OK** para fechar a janela **Propriedades**. 
    

