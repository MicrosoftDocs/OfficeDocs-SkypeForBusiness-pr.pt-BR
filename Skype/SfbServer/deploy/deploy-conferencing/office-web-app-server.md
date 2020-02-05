---
title: Configurar a integração com o servidor do Office Web Apps no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Resumo: Leia este tópico para obter informações sobre como configurar a integração entre o servidor do Office Web Apps e o Skype for Business Server para habilitar apresentações do PowerPoint para Webconferência Web.'
ms.openlocfilehash: b20646f31a7925ca66180c1580751574152047e5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768344"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurar a integração com o servidor do Office Web Apps no Skype for Business Server
 
**Resumo:** Leia este tópico para obter informações sobre como configurar a integração entre o Office Web Apps Server e o Skype for Business Server para habilitar apresentações do PowerPoint para Webconferência Web.
  
O Skype for Business Server emprega o servidor do Office Web Apps para manipular apresentações do PowerPoint para conferências na Web. Para obter informações sobre as vantagens dessa abordagem, consulte [planejar a conferência no Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Antes de configurar o Skype for Business Server para usar o Office Web Apps Server, você deve certificar-se de que o Office Web Apps Server já está implantado e configurado. Para obter informações sobre o Office Web Apps Server, consulte o artigo [implantar a infraestrutura: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Após a instalação bem-sucedida do Office Web Apps Server e sua Web farm configurada corretamente, você deve configurar o Skype for Business Server para se comunicar com o novo servidor, adicionando a URL de descoberta do servidor do Office Web Apps ao seu Skype for Business Topologia do servidor. 
  
> [!NOTE]
> A iteração mais recente do Office Web Apps Server é chamada Office Online Server, que é compatível com o Skype for Business Server. Para obter mais detalhes, consulte a [documentação do Office Online Server](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurar o Skype for Business Server para se comunicar com o servidor do Office Web Apps

Para adicionar o Servidor do Office Web Apps à sua topologia, execute estas etapas:
  
1. Abrir o construtor de topologias do Skype for Business Server.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo  **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa  **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.
    
4. No Construtor de Topologias, expanda o **Skype for Business Server**, expanda o nome do seu site, expanda **Pools de Front-Ends Enterprise Edition**, clique com o botão direito do mouse no nome de um dos seus pools e depois em **Editar Propriedades**.
    
5. Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor do Office Web Apps** e clique em **Novo** (ou selecione um Servidor do Office Web Apps existente na lista suspensa).
    
6. Na caixa de diálogo **Definir Novo Servidor do Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor do Office Web Apps na caixa **FQDN do Servidor do Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor do Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor do Office Web Apps**.
    
   - Se o Office Web Apps Server estiver instalado no local e na mesma zona de rede que o Skype for Business Server, então a opção **Office Web Apps Server é implantada em uma rede externa (ou seja, perímetro/Internet)** não deve ser selecionada.
    
   - Se o Servidor do Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor do Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.
    
7. Na caixa de diálogo **definir novo Office Web Apps Server** , clique em **OK**e, em seguida, clique em **OK** na caixa de diálogo **Editar propriedades** . A URL de descoberta será então listada como uma das associações do pool.
    
Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor do Office Web Apps.
  
Depois que você adicionar a URL de descoberta à topologia, terá que publicar a topologia atualizada. Para isso, no Construtor de Topologias:
  
1. Clique em **Ação** e depois em **Publicar Topologia**.
    
2. No assistente Publicar topologia, na página **Publicar a Topologia**, clique em **Avançar**.
    
3. Na página **Assistente de publicação concluído**, clique em **Concluir**.
    
4. Feche o Construtor de Topologias.
    
## <a name="configure-access-for-external-users"></a>Configurar o acesso para usuários externos

Se você quiser que os usuários externos (ou seja, os usuários que estão fazendo logon fora do firewall da sua organização) tenham acesso às apresentações do PowerPoint para servidor Web Apps do Office, será necessário usar o Office Web Apps Server e um servidor proxy reverso. Também será necessário criar e configurar uma regra de publicação de site, que ajudará a assegurar que os usuários possam se conectar ao servidor. 
  
## <a name="validate-the-configuration"></a>Validar a configuração

Após a publicação do Office Web Apps Server na topologia e após a publicação da topologia, você verá dois novos eventos do log de eventos no log de eventos do Skype for Business Server. Primeiro, um evento LS Data MCU (ID 41034) deve ser adicionado; esse evento relatará que o Servidor do Office Web Apps foi descoberto:
  
 **O Servidor do Office Web Apps do servidor de webconferência foi descoberto, o conteúdo do PowerPoint está habilitado.**
  
Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:
  
 **Descoberta bem-sucedida do Servidor do Office Web Apps dp Servidor de Conferência da Web.**
  
 **Página do apresentador interno do servidor do https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampOffice Web Apps:; embed =**
  
 **Página de participantes internos do servidor do Office https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&ampWeb Apps:; embed = true&amp;=**
  
Se você tiver configurado o acesso para usuários externos, também verá algo semelhante a:
  
 **Página do apresentador externo do Office Web https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampapps Server:; inserir**
  
 **Página de participantes internos do servidor do Office <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>Web Apps:;**
  
Se você vir um evento de MCU de dados LS com a ID do evento 41033, isso significa que o descobrimento do servidor do Office Web Apps falhou. Nesse caso, o Skype for Business Server tentará quantas vezes forem necessárias para descobrir o servidor Office Web Apps recém configurado. Se o processo de descoberta falhar repetidamente, remova o servidor do Office Web Apps do documento de topologia, publique a topologia atualizada e tente adicionar o servidor do Office Web Apps novamente à topologia após a resolução dos problemas de conectividade.
  
Se o Office Web Apps Server parece estar configurado corretamente e foi reconhecido pelo processo de descoberta, você pode verificar se o servidor do Office Web Apps está funcionando como esperado compartilhando uma apresentação do PowerPoint entre um par de clientes do Skype for Business. Se o usuário A conseguir carregar e exibir a apresentação do PowerPoint e se o usuário B puder entrar na reunião e ver essa apresentação, o Office Web Apps Server está funcionando.
  
Mesmo que o Office Web Apps Server pareça estar configurado corretamente, você pode possivelmente receber a mensagem de erro "alguns recursos de compartilhamento estão indisponíveis devido a problemas de conectividade do servidor" quando você tenta compartilhar uma apresentação do PowerPoint. Se você receber a mensagem de erro, reinicie o servidor front-end (ou servidores) associado ao novo servidor do Office Web Apps.
  

