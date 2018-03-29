---
title: Configurar a integração com o Servidor do Office Web Apps no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Resumo: Leia este tópico para saber como configurar a integração entre o Office Web Apps Server e Skype para Business Server 2015 para habilitar apresentações do PowerPoint para Webconferência.'
ms.openlocfilehash: da6b5765cf62fc97fcc20b72e2411db306b37f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server-2015"></a>Configurar a integração com o Servidor do Office Web Apps no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como configurar a integração entre o Office Web Apps Server e Skype para Business Server 2015 para habilitar apresentações do PowerPoint para Webconferência.
  
Skype para Business Server emprega o Office Web Apps Server para lidar com apresentações do PowerPoint para Webconferência. Para obter informações sobre as vantagens para essa abordagem, consulte [Planejar a conferência em Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md).
  
Antes de você poder configurar Skype para Business Server usar o Office Web Apps Server, você deve assegurar que os Office Web Apps Server já foi implantada e configurada. Para obter informações sobre o Office Web Apps Server, consulte o artigo [implantar a infraestrutura: servidor do Office Online](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Depois que o Office Web Apps Server foi instalado com êxito e seu farm de Web foi configurado corretamente, em seguida, você deve configurar Skype para Business Server para se comunicar com o novo servidor, adicionando a URL de descoberta do Office Web Apps Server à sua Skype para negócios Topologia de servidor. 
  
> [!NOTE]
> A iteração mais recente do Office Web Apps Server é nomeada Office Online Server, que é suportado pelo Skype para Business Server 2015. Para obter mais detalhes, consulte a [documentação do servidor do Office Online](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurar Skype para Business Server para se comunicar com o Office Web Apps Server

Para adicionar o Servidor do Office Web Apps à sua topologia, execute estas etapas:
  
1.  Abra o Skype do construtor de topologia de servidor de negócios.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo  **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa  **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.
    
4. No Construtor de Topologias, expanda o **Skype for Business Server**, expanda o nome do seu site, expanda **Pools de Front-Ends Enterprise Edition**, clique com o botão direito do mouse no nome de um dos seus pools e depois em **Editar Propriedades**.
    
5. Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor do Office Web Apps** e clique em **Novo** (ou selecione um Servidor do Office Web Apps existente na lista suspensa).
    
6. Na caixa de diálogo **Definir Novo Servidor do Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor do Office Web Apps na caixa **FQDN do Servidor do Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor do Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor do Office Web Apps**.
    
  - Se o Office Web Apps Server for instalado no local e na mesma zona do Skype para Business Server, em seguida, a opção **que Office Web Apps Server é implantado em uma rede externa (ou seja, de perímetro/Internet)** não deve ser selecionado.
    
  - Se o Servidor do Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor do Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.
    
7. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, clique em **OK** e em **OK** na caixa de diálogo **Editar Propriedades**. Em seguida, a URL de descoberta do Office Online será listada como uma das associações do pool.
    
Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor do Office Web Apps.
  
Depois que você adicionar a URL de descoberta à topologia, terá que publicar a topologia atualizada. Para isso, no Construtor de Topologias:
  
1. Clique em **Ação** e depois em **Publicar Topologia**.
    
2. No assistente Publicar topologia, na página **Publicar a Topologia**, clique em **Avançar**.
    
3. Na página **Assistente de publicação concluído**, clique em **Concluir**.
    
4. Feche o Construtor de Topologias.
    
## <a name="configure-access-for-external-users"></a>Configurar o acesso para usuários externos

Se você quiser (ou seja, usuários logon de fora do firewall da organização) de usuários externos acessem de apresentações do PowerPoint do Office Web Apps Server, em seguida, você precisará usar o Office Web Apps Server e um servidor proxy reverso. Também será necessário criar e configurar uma regra de publicação de site, que ajudará a assegurar que os usuários possam se conectar ao servidor. 
  
## <a name="validate-the-configuration"></a>Validar a configuração

Depois que o Office Web Apps Server foi adicionado à topologia e depois que tiver sido publicada nessa topologia, você deverá ver dois novos eventos de log de eventos no Skype para o log de eventos do servidor de negócios. Primeiro, um evento LS Data MCU (ID 41034) deve ser adicionado; esse evento relatará que o Servidor do Office Web Apps foi descoberto:
  
 **O Servidor do Office Web Apps do servidor de webconferência foi descoberto, o conteúdo do PowerPoint está habilitado.**
  
Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:
  
 **Descoberta bem-sucedida do Servidor do Office Web Apps dp Servidor de Conferência da Web.**
  
 **Página interna do apresentador do Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0 &amp;incorporar =**
  
 **Página interna do Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0 &amp;incorporar = true&amp;=**
  
Se você configurou o acesso para usuários externos, também verá algo semelhante ao seguinte:
  
 **Página externa do apresentador do Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0 &amp;incorporar**
  
 **Página interna do Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0 &amp;incorporar = true&amp;**
  
Se você vir um evento de LS dados MCU com a identificação de evento do 41033 o que significa que a descoberta de Office Web Apps Server falhou. Nesse caso, Skype para Business Server tentará quantas vezes forem necessárias para descobrir o recentemente configurado Office Web Apps Server. Se o processo de descoberta falhar repetidamente você deve remover o Office Web Apps Server do seu documento de topologia, publicar a topologia atualizada e tente adicionar o Office Web Apps Server volta para a topologia após os problemas de conectividade foram resolvidos.
  
Se o Office Web Apps Server parece estar configurado corretamente e se foi reconhecido pelo processo de descoberta, você pode verificar se o Office Web Apps Server está funcionando conforme o esperado, compartilhando uma apresentação do PowerPoint entre um par de Skype para clientes corporativos. Se o usuário A pode carregar e exibir a apresentação do PowerPoint e se o usuário B pode ingressar na reunião e consulte essa apresentação Office Web Apps Server está funcionando.
  
Mesmo que o Office Web Apps Server parece estar configurado corretamente, você poderia potencialmente receber a mensagem de erro "alguns recursos de compartilhamento não estão disponíveis devido a problemas de conectividade de servidor" ao tentar compartilhar uma apresentação do PowerPoint. Se você receber essa mensagem de erro, que você deve reiniciar o Front-End server (ou servidores) associado ao novo Office Web Apps Server.
  

