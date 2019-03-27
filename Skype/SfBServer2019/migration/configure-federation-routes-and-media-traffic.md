---
title: Configurar rotas de federação e tráfego de mídia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários em organizações separadas se comuniquem pelos limites da rede. Após migrar para o seu pool piloto, você precisa fazer a transição da rota de Federação dos seus servidores de borda de versões anteriores para a rota de federação de sua Skype para servidores de borda de 2019 Business Server.
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880225"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurar rotas de federação e tráfego de mídia

A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários em organizações separadas se comuniquem pelos limites da rede. Após migrar para o seu pool piloto, você precisa fazer a transição da rota de Federação da versão anterior servidores de borda para a rota de federação de sua Skype para servidores de borda de 2019 Business Server.
  
Use os procedimentos a seguir para fazer a transição da rota de Federação e a rota do tráfego de mídia do servidor de borda e diretor de sua versão anterior para sua Skype para o servidor de borda do Business Server 2019, para uma implantação local único.
  
> [!IMPORTANT]
> Alterando a rota de Federação e a rota do tráfego de mídia requer que você agendar o tempo de inatividade de manutenção para o Skype para Business Server 2019 e servidores de borda de versão anterior. Esse processo de transição inteira também significa que acesso federado estará indisponível durante a interrupção. Você deve agendar o tempo de inatividade por um período quando você espera que a atividade mínima do usuário. Você também deve fornecer notificação suficiente para seus usuários finais. Planeje apropriadamente para este interrupção e o conjunto apropriado expectativas dentro da sua organização. 
  
> [!IMPORTANT]
> Se o seu servidor de borda herdado está configurado para usar o mesmo FQDN para o serviço de borda de acesso, serviço de borda de webconferência e A / não há suporte para o serviço de borda de V, os procedimentos nesta seção. Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, primeiro você precisa migrar todos os seus usuários e encerre as servidor de borda de versões anteriores antes de habilitar a federação no Skype para servidor de borda de 2019 Business Server. 
  
> [!IMPORTANT]
> Se sua federação XMPP é encaminhada por um Skype para o servidor de borda de 2019 Business Server, os usuários da versão anterior não será capazes de se comunicar com um parceiro federado XMPP até que todos os usuários foram movidos para Skype para Business Server 2019, políticas XMPP e certificados tiverem sido configurados, parceiro federado XMPP tiver sido configurado no Skype para Business Server 2019 e, por fim, as entradas DNS foram atualizadas. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Para remover a associação de Federação herdada do Skype para sites corporativos Server 2019

1. No Skype para o servidor de negócios 2019 Front-End Server, abra a topologia existente no construtor de topologia. 
    
2. No painel esquerdo, navegue até o nó do site, que está localizado diretamente abaixo **Skype para Business Server**.
    
3. Com o botão direito do site e, em seguida, clique em **Editar propriedades**.
    
4. No painel esquerdo, selecione **rota de Federação**. 
    
5. Em **atribuição de rota de Federação do Site**, desmarque a caixa de seleção **Habilitar federação SIP** para desabilitar a rota de Federação através do ambiente herdado. 
  
6. Clique em **Okey** para fechar a página Editar propriedades. 
    
7. A partir do **Construtor de topologias**, selecione o nó superior **Skype para Business Server**.
    
8. No menu **ação** , clique em **Publicar topologia**.
    
9. Clique em **Avançar** para concluir o processo de publicação e clique em **Concluir** quando o processo de publicação for concluído. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Para configurar o servidor de borda herdado como um servidor de borda não federado

1. No painel esquerdo, navegue até o nó install herdado e, em seguida, para o nó **pools de borda** . 
    
2. Com o botão direito no servidor de borda e, em seguida, clique em **Editar propriedades**.
    
3. Selecione **Geral** no painel à esquerda. 
    
4. Desmarque a caixa de seleção **Habilitar federação para este pool de borda (porta 5061)** e selecione **Okey** para fechar a página. 
  
5. No menu **ação** , selecione **Publicar topologia**e clique em **Avançar**.
    
6. Quando o **Assistente para publicação** for concluído, clique em **Concluir** para fechar o assistente. 
    
7. Verifique se a federação para o servidor de borda herdado está desabilitada no construtor de topologia.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Para configurar certificados no servidor de borda herdado

1. Exporte o certificado externo do Proxy de acesso, com a chave privada, do servidor de borda herdado. 
    
2. Sobre o Skype para servidor de borda do Business Server 2019 e importação de certificado externo do Proxy de acesso da etapa anterior.
    
3. Atribua o certificado externo do Proxy de acesso para o Skype para Business Server 2019 a interface externa do servidor de borda.
    
4. O certificado da interface interna do Skype para o servidor de borda de 2019 Business Server deve ser solicitado por uma autoridade de certificação confiável e atribuído. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Para alterar a rota de Federação da versão anterior para usar Skype para o servidor de borda do Business Server 2019

1. No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype para Business Server 2019** e, depois, para o nó **pools de borda** . 
    
2. Com o botão direito no servidor de borda e, em seguida, clique em **Editar propriedades**.
    
3. Selecione **Geral** no painel à esquerda. 
    
4. Marque a caixa de seleção para **Habilitar a federação para este pool de borda (porta 5061)** e, em seguida, clique em **Okey** para fechar a página. 
  
5. No menu **ação** , selecione **Publicar topologia**e clique em **Avançar**.
    
6. Quando o **Assistente para publicação** for concluído, clique em **Concluir** para fechar o assistente. 
    
7. Verifique se **federação (porta 5061)** está definido como **Enabled** no construtor de topologia.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Para atualizar o Skype para o próximo salto da federação de servidor de borda do Business Server 2019

1. No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype para Business Server 2019** e, depois, para o nó **pools de borda** . 
    
2. Expanda o nó, clique com o botão o servidor de borda listado e clique em **Editar propriedades**. 
    
3. Na página **Geral** , em **seleção do próximo salto**, selecione na lista suspensa o Skype para Business Server 2019 pool.
  
4. Clique em **Okey** para fechar a página Editar propriedades. 
    
5. A partir do **Construtor de topologias**, selecione o nó superior **Skype para Business Server**. 
    
6. No menu **ação** , clique em **Publicar topologia** e conclua o assistente. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Para configurar o Skype para o caminho de mídia de saída do servidor de borda do Business Server 2019

1. No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype para Business Server 2019** e, depois, para o pool abaixo de **pools de Front End do Enterprise Edition**ou **Standard Edition servidores Front-End** .
    
2. Com o botão direito do pool e, em seguida, clique em **Editar propriedades**.
    
3. Na seção **associações** , marque a caixa de seleção **associar pool de borda (para componentes de mídia)** . 
  
4. Na caixa de lista suspensa, selecione o Skype para servidor de borda de 2019 Business Server.
    
5. Clique em **Okey** para fechar a página **Editar propriedades** . 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Para ativar Skype para federação do servidor de borda do Business Server 2019

1. No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype para Business Server 2019** e, depois, para o nó **pools de borda** . 
    
2. Expanda o nó, clique com o botão o servidor de borda listado e clique em **Editar propriedades**. 
    
    > [!NOTE]
    > Federação só pode ser habilitada para um único pool de borda. Se você tiver vários pools de borda, selecione um para usar como o pool de borda federating. 
  
3. Na página **Geral** , verifique se que a caixa de seleção **Habilitar federação para este pool de borda (porta 5061)** está selecionada. 
  
4. Clique em **Okey** para fechar a página Editar propriedades. 
    
5. Navegue até o nó do site. 
    
6. Com o botão direito do site e, em seguida, clique em **Editar propriedades**.
    
7. No painel esquerdo, clique em **rota de Federação**.
    
8. Em **atribuição de rota de Federação do Site**, selecione **Habilitar federação SIP**e, em seguida, na lista Selecione o Skype para o servidor de borda do Business Server 2019 listados. 
  
9. Clique em **Okey** para fechar a página **Editar propriedades** . 
    
     Para implantações de vários locais, conclua este procedimento em cada site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Para publicar as alterações de configuração do servidor de borda

1. A partir do **Construtor de topologias**, selecione o nó superior **Skype para Business Server**. 
    
2. No menu **ação** , selecione **Publicar topologia** e conclua o assistente. 
    
3. Aguarde a replicação do Active Directory ocorra em todos os pools na implantação.
    
    > [!NOTE]
    > Você pode ver a seguinte mensagem: **Aviso: A topologia contém mais de um servidor de borda federados. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um servidor de borda seria usado ativamente para federação. Verifique se o registro SRV de DNS aponta para o servidor de borda correto. Se desejar implantar vários federação de servidor de borda a ser ativo simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados são usando Skype para Business Server. Verifique se o registro SRV de DNS lista todos os servidores de borda de Federação habilitada.** Esse aviso é esperado e pode ser ignorado com segurança. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Para configurar o Skype para o servidor de borda do Business Server 2019

1. Colocar todas a Skype para os servidores de borda do Business Server 2019 on-line. 
    
2. Atualizar as regras de roteamento do firewall externo ou as configurações de Balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente, a porta 443) e federação (geralmente, a porta 5061) para o Skype para negócios 2019 borda Server, em vez do servidor de borda herdado.
    
    > [!NOTE]
    > Se você não tiver um balanceador de carga de hardware, você precisará atualizar o registro DNS A para federação resolver para o novo Skype para o servidor de borda de acesso do servidor de negócios. Para realizar isso com um mínimo de interrupção, reduza o valor TLL para o Skype externo para o FQDN de borda de acesso do Business Server para que ao DNS é atualizado para apontar para o novo Skype para borda de acesso do servidor de negócios, Federação e acesso remoto serão atualizados rapidamente. 
  
3. Pare o **Skype para borda de acesso do servidor de negócios** de cada computador do servidor de borda. 
    
4. Em cada computador do servidor de borda herdado, abra o miniaplicativo **Serviços** em **Ferramentas administrativas**.
    
5. Na lista de serviços, encontre **Skype para borda de acesso do servidor de negócios**.
    
6. Nome do serviço do mouse em e selecione **Parar** para parar o serviço. 
    
7. Defina o tipo de inicialização para **desabilitado**. 
    
8. Clique em **Okey** para fechar a janela **Propriedades** . 
    

