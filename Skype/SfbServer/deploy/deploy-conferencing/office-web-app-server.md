---
title: Configurar a integração com Office Web Apps Server no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Resumo: leia este tópico para saber como configurar a integração entre Office Web Apps Server e Skype for Business Server para habilitar PowerPoint apresentações para webconferência.'
ms.openlocfilehash: 291e246651a5c4f909f2e739e76de65d8c983c5b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835949"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurar a integração com Office Web Apps Server no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar a integração entre Office Web Apps Server e Skype for Business Server para habilitar PowerPoint apresentações para webconferência.
  
Skype for Business Server emprega o Office Web Apps para lidar com PowerPoint apresentações para webconferência. Para obter informações sobre as vantagens dessa abordagem, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Antes de configurar o Skype for Business Server para usar Office Web Apps Server, você deve garantir que o servidor Office Web Apps já está implantado e configurado. Para obter informações sobre Office Web Apps Server, consulte o artigo [Implantar a infraestrutura: Servidor do Office Online](/webappsserver/deploy-the-infrastructure-office-web-apps-server). 
  
Depois que Office Web Apps Server tiver sido instalado com êxito e seu farm web configurado corretamente, você deve configurar o Skype for Business Server para se comunicar com o novo servidor adicionando a URL de descoberta do Office Web Apps Server à sua topologia do Skype for Business Server. 
  
> [!NOTE]
> A iteração mais recente do Office Web Apps Server é chamada Servidor do Office Online, que é suportada por Skype for Business Server. Para obter mais detalhes, consulte a [documentação Servidor do Office Online .](/officeonlineserver/office-online-server) 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurar Skype for Business Server para se comunicar com Office Web Apps Server

Para adicionar Office Servidor Web Apps à sua topologia, conclua as seguintes etapas:
  
1. Abra Skype for Business Server Construtor de Topologias.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar Topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.
    
4. No Construtor de Topologias, expanda **Skype for Business Server,** expanda o nome do seu site, expanda Edição Enterprise **pools de Front-End,** clique com o botão direito do mouse no nome de um de seus pools e clique em **Editar Propriedades**.
    
5. Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor Office Web Apps** e clique em **Novo** (ou selecione um Servidor Office Web Apps existente na lista suspensa).
    
6. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor Office Web Apps na caixa **FQDN do Servidor Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor Office Web Apps**.
    
   - Se o servidor Office Web Apps estiver instalado no local e na mesma zona de rede do Skype for Business Server, a opção Office Web Apps Server será implantada em uma rede externa **(ou seja, perímetro/Internet)** não deverá ser selecionada.
    
   - Se o Servidor Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.
    
7. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, clique em **OK** e depois em **OK** na caixa de diálogo **Editar Propriedades**. Em seguida, a URL de descoberta será listada como uma das Associações do pool.
    
Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor Office Web Apps.
  
Depois de adicionar a URL de descoberta à topologia, você deve publicar a topologia atualizada. Para isso, no Construtor de Topologias:
  
1. Clique em **Ação** e depois em **Publicar Topologia**.
    
2. No assistente Publicar Topologia, na página **Publicar a topologia**, clique em **Avançar**.
    
3. Na página **Assistente de publicação concluído**, clique em **Concluir**.
    
4. Feche o Construtor de Topologias.
    
## <a name="configure-access-for-external-users"></a>Configurar o acesso para usuários externos

Se você quiser que os usuários externos (ou seja, usuários fazendo logom de fora do firewall da sua organização) tenham acesso Office apresentações do PowerPoint Web Apps Server, então você precisará usar o servidor Web Apps do Office e um servidor proxy reverso. Você também precisará criar e configurar uma regra de publicação de site, o que ajudará a garantir que os usuários sejam capazes de se conectar ao servidor. 
  
## <a name="validate-the-configuration"></a>Validar a configuração

Depois Office Servidor Web Apps tiver sido adicionado à topologia e depois que a topologia tiver sido publicada, você deverá ver dois novos eventos de log de eventos no log de eventos Skype for Business Server. Primeiro, um evento LS Data MCU (ID do evento 41034) deve ser adicionado; esse evento informará que o servidor Office Web Apps foi descoberto:
  
 **O Servidor de WebConferência Office Servidor web apps é descoberto, PowerPoint conteúdo está habilitado.**
  
Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:
  
 **A descoberta do Servidor Office Web Apps Server foi bem-sucedida.**
  
 **Office Página do apresentador interno do Servidor web apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;inbed=**
  
 **Office Página do participante interno do Servidor web apps: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**
  
Se você configurou o acesso para usuários externos, também verá algo semelhante a:
  
 **Office Página de apresentador externo do Servidor web apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;inbed**
  
 **Office Página do participante interno do Servidor web apps: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
Se você ver um evento LS Data MCU com o ID 41033, significa que a descoberta do Office Web Apps Server falhou. Nesse caso, Skype for Business Server tentará quantas vezes for necessário para descobrir o servidor web apps recém-configurado Office Web Apps. Se o processo de descoberta falhar repetidamente, você deve remover o Office Web Apps Server do seu documento de topologia, publicar a topologia atualizada e tentar adicionar o Office Web Apps Server novamente à topologia depois que os problemas de conectividade tiverem sido resolvidos.
  
Se o Office Web Apps Server parecer estar configurado corretamente e tiver sido reconhecido pelo processo de descoberta, você poderá verificar se o servidor do Office Web Apps está funcionando conforme esperado compartilhando uma apresentação PowerPoint entre um par de clientes Skype for Business. Se o Usuário A puder carregar e exibir a apresentação do PowerPoint e se o Usuário B puder participar da reunião e ver a apresentação, então o Office Web Apps Server está funcionando.
  
Mesmo que Office Servidor Web Apps pareça estar configurado corretamente, você pode receber a mensagem de erro "Alguns recursos de compartilhamento estão indisponíveis devido a problemas de conectividade do servidor" ao tentar compartilhar uma apresentação PowerPoint servidor. Se você receber essa mensagem de erro, você deve reiniciar o servidor (ou servidores) de Front End associados ao novo Office Web Apps Server.
