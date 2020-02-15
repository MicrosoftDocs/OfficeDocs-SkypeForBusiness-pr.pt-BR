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
description: 'Resumo: Leia este tópico para saber como configurar a integração entre o Office Web Apps Server e o Skype for Business Server para habilitar apresentações do PowerPoint para Webconferência.'
ms.openlocfilehash: fee5939e8441457e3cee66e266baacd144ada288
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983916"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurar a integração com o servidor do Office Web Apps no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar a integração entre o Office Web Apps Server e o Skype for Business Server para habilitar apresentações do PowerPoint para Webconferência.
  
O Skype for Business Server emprega o servidor do Office Web Apps para lidar com apresentações do PowerPoint para Webconferência. Para obter informações sobre as vantagens dessa abordagem, consulte [Plan for Conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Antes de poder configurar o Skype for Business Server para usar o servidor do Office Web Apps, você deve garantir que o servidor do Office Web Apps já esteja implantado e configurado. Para saber mais sobre o servidor do Office Web Apps, confira o artigo [implantar a infraestrutura: servidor do Office Online](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Após o servidor do Office Web Apps ter sido instalado com êxito e seu farm da Web corretamente configurado, você deve configurar o Skype for Business Server para se comunicar com o novo servidor adicionando a URL de descoberta do Office Web Apps Server ao Skype for Business Topologia do servidor. 
  
> [!NOTE]
> A iteração mais recente do servidor do Office Web Apps é chamada de servidor do Office Online, que é compatível com o Skype for Business Server. Para obter mais detalhes, consulte a [documentação do servidor do Office Online](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurar o Skype for Business Server para se comunicar com o servidor do Office Web Apps

Para adicionar o servidor do Office Web Apps à sua topologia, conclua as seguintes etapas:
  
1. Abra o construtor de topologias do Skype for Business Server.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar Topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.
    
4. No construtor de topologias, expanda o **Skype for Business Server**, expanda o nome do seu site, expanda **pools de front-ends Enterprise Edition**, clique com o botão direito do mouse no nome de um dos seus pools e clique em **Editar propriedades**.
    
5. Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor Office Web Apps** e clique em **Novo** (ou selecione um Servidor Office Web Apps existente na lista suspensa).
    
6. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor Office Web Apps na caixa **FQDN do Servidor Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor Office Web Apps**.
    
   - Se o servidor do Office Web Apps estiver instalado no local e na mesma zona de rede que o Skype for Business Server, a opção do **servidor do Office Web Apps é implantada em uma rede externa (ou seja, o perímetro/Internet)** não deve ser selecionada.
    
   - Se o Servidor Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.
    
7. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, clique em **OK** e depois em **OK** na caixa de diálogo **Editar Propriedades**. A URL de descoberta será listada como uma das associações do pool.
    
Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor Office Web Apps.
  
Depois de adicionar a URL de descoberta à topologia, você deve publicar a topologia atualizada. Para isso, no Construtor de Topologias:
  
1. Clique em **Ação** e depois em **Publicar Topologia**.
    
2. No assistente Publicar Topologia, na página **Publicar a topologia**, clique em **Avançar**.
    
3. Na página **Assistente de publicação concluído**, clique em **Concluir**.
    
4. Feche o Construtor de Topologias.
    
## <a name="configure-access-for-external-users"></a>Configurar o acesso para usuários externos

Se você deseja que usuários externos (ou seja, usuários que fazem logon de fora do firewall da sua organização) tenham acesso a apresentações do PowerPoint para o servidor do Office Web Apps, será necessário usar o servidor do Office Web Apps e um servidor de proxy reverso. Você também precisará criar e configurar uma regra de publicação de site, o que ajudará a garantir que os usuários possam se conectar ao servidor. 
  
## <a name="validate-the-configuration"></a>Validar a configuração

Depois que o servidor do Office Web Apps tiver sido adicionado à topologia e depois que essa topologia tiver sido publicada, você verá dois eventos de log de eventos novos no log de eventos do Skype for Business Server. Primeiro, um evento MCU de dados de LS (ID de evento 41034) deve ser adicionado; Este evento relatará que o servidor do Office Web Apps foi descoberto:
  
 **Servidor de conferência da Web o servidor do Office Web Apps é descoberto, o conteúdo do PowerPoint está habilitado.**
  
Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:
  
 **Descoberta bem-sucedida do servidor do Office Web Apps do servidor de Webconferência.**
  
 **Página interna do apresentador do servidor do https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampOffice Web Apps:; embed =**
  
 **Página de participantes internos do servidor do Office https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&ampWeb Apps:; embed = true&amp;=**
  
Se você tiver configurado o acesso para usuários externos, verá também algo semelhante a:
  
 **Página do apresentador externo do servidor do https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampOffice Web Apps:; embed**
  
 **Página de participantes internos do servidor do Office <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>Web Apps:;**
  
Se você ver um evento LS Data MCU com o ID 41033, significa que a descoberta do Office Web Apps Server falhou. Nesse caso, o Skype for Business Server tentará quantas vezes forem necessárias para descobrir o servidor do Office Web Apps recém configurado. Se o processo de descoberta falhar repetidamente, você deve remover o Office Web Apps Server do seu documento de topologia, publicar a topologia atualizada e tentar adicionar o Office Web Apps Server novamente à topologia depois que os problemas de conectividade tiverem sido resolvidos.
  
Se o servidor do Office Web Apps parece estar configurado corretamente e foi reconhecido pelo processo de descoberta, é possível verificar se o servidor do Office Web Apps está funcionando conforme o esperado, compartilhando uma apresentação do PowerPoint entre um par de clientes do Skype for Business. Se o Usuário A puder carregar e exibir a apresentação do PowerPoint e se o Usuário B puder participar da reunião e ver a apresentação, então o Office Web Apps Server está funcionando.
  
Mesmo que o servidor do Office Web Apps pareça estar configurado corretamente, você poderia possivelmente receber a mensagem de erro "alguns recursos de compartilhamento estão indisponíveis devido a problemas de conectividade do servidor" quando você tenta compartilhar uma apresentação do PowerPoint. Se você receber essa mensagem de erro, você deve reiniciar o servidor (ou servidores) de Front End associados ao novo Office Web Apps Server.
  

