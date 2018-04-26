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
description: 'Summary: Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server 2015 to enable PowerPoint presentations for web conferencing.'
ms.openlocfilehash: da6b5765cf62fc97fcc20b72e2411db306b37f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server-2015"></a>Configurar a integração com o Servidor do Office Web Apps no Skype for Business Server 2015
 
**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server 2015 to enable PowerPoint presentations for web conferencing.
  
Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing. For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md).
  
Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured. For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology. 
  
> [!NOTE]
> The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server 2015. Para obter mais detalhes, consulte a documentação do [Servidor do Office Onlinehttps://technet.microsoft.com/pt-br/library/jj219456(v=office.16).aspx](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Skype for Business Server 2015: Configurar a integração com o Servidor do Office Web Apps

Para adicionar o Servidor do Office Web Apps à sua topologia, execute estas etapas:
  
1.  Open Skype for Business Server Topology Builder.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo  **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa  **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.
    
4. No Construtor de Topologias, expanda o **Skype for Business Server**, expanda o nome do seu site, expanda **Pools de Front-Ends Enterprise Edition**, clique com o botão direito do mouse no nome de um dos seus pools e depois em **Editar Propriedades**.
    
5. Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor do Office Web Apps** e clique em **Novo** (ou selecione um Servidor do Office Web Apps existente na lista suspensa).
    
6. Na caixa de diálogo **Definir Novo Servidor do Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor do Office Web Apps na caixa **FQDN do Servidor do Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor do Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor do Office Web Apps**.
    
  - Se o Servidor do Office Web Apps estiver instalado localmente e na mesma zona de rede que o , a opção O Servidor do Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet) não deverá ser selecionada.
    
  - Se o Servidor do Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor do Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.
    
7. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, clique em **OK** e em **OK** na caixa de diálogo **Editar Propriedades**. Em seguida, a URL de descoberta do Office Online será listada como uma das associações do pool.
    
Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor do Office Web Apps.
  
Depois que você adicionar a URL de descoberta à topologia, terá que publicar a topologia atualizada. Para isso, no Construtor de Topologias:
  
1. Clique em **Ação** e depois em **Publicar Topologia**.
    
2. No assistente Publicar topologia, na página **Publicar a Topologia**, clique em **Avançar**.
    
3. Na página **Assistente de publicação concluído**, clique em **Concluir**.
    
4. Feche o Construtor de Topologias.
    
## <a name="configure-access-for-external-users"></a>Configurar o acesso para usuários externos

Se você quiser que usuários externos (ou seja, que se conectam de fora do firewall da organização) tenham acesso a apresentações do PowerPoint do  PowerPoint, será necessário usar o  e um servidor de proxy reverso. Também será necessário criar e configurar uma regra de publicação de site, que ajudará a assegurar que os usuários possam se conectar ao servidor. 
  
## <a name="validate-the-configuration"></a>Validar a configuração

Após a adição do  à topologia, e após a publicação da topologia, você deverá ver dois novos eventos no log de eventos do . Primeiro, um evento LS Data MCU (ID 41034) deve ser adicionado; esse evento relatará que o Servidor do Office Web Apps foi descoberto:
  
 **O Servidor do Office Web Apps do servidor de webconferência foi descoberto, o conteúdo do PowerPoint está habilitado.**
  
Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:
  
 **Descoberta bem-sucedida do Servidor do Office Web Apps dp Servidor de Conferência da Web.**
  
 Página do apresentador interna do Servidor do Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&embed=
  
 Página do participante interna do Servidor do Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&embed=true&=
  
Se você configurou o acesso para usuários externos, também verá algo semelhante ao seguinte:
  
 Página do apresentador externa do Servidor do Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&embed
  
 Página do participante interna do Servidor do Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&embed=true&=
  
Se você vir um evento LS Data MCU com o ID 41033, significa que a descoberta do  falhou. In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server. Se o processo de descoberta falhar repetidamente, você deve remover o Servidor do Office Web Apps do seu documento de topologia, publicar a topologia atualizada e tentar adicionar o  novamente à topologia depois que os problemas de conectividade tiverem sido resolvidos.
  
Se o  parecer estar configurado corretamente e tiver sido reconhecido pelo processo de descoberta, é possível verificar se o  está funcionando conforme o esperado compartilhando uma apresentação do PowerPoint entre um par de clientes do  . Se o Usuário A puder carregar e exibir a apresentação do PowerPoint e se o Usuário B puder participar da reunião e ver a apresentação, então o  está funcionando.
  
Mesmo que o pareça estar configurado corretamente, é possível receber a mensagem de erro “Alguns recursos de compartilhamento não estão disponíveis devido a problemas de conectividade do servidor” ao tentar compartilhar uma apresentação do PowerPoint. Se você receber essa mensagem de erro, você deve reiniciar o servidor (ou servidores) de Front End associados ao novo .
  

