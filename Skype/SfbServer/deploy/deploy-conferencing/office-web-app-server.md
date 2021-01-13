---
title: Configurar a integração com o Servidor do Office Web Apps no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Resumo: Leia este tópico para saber como configurar a integração entre o Servidor do Office Web Apps e o Skype for Business Server para habilitar apresentações do PowerPoint para webconferência.'
ms.openlocfilehash: 005bd9fe7d7fece7d488935002e7146fc5a9ffe4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820461"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Configurar a integração com o Servidor do Office Web Apps no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar a integração entre o Servidor do Office Web Apps e o Skype for Business Server para habilitar apresentações do PowerPoint para webconferência.
  
O Skype for Business Server emprega o Servidor do Office Web Apps para lidar com apresentações do PowerPoint para webconferência. Para obter informações sobre as vantagens dessa abordagem, consulte [Planejar conferências no Skype for Business Server.](../../plan-your-deployment/conferencing/conferencing.md)
  
Antes de configurar o Skype for Business Server para usar o Servidor do Office Web Apps, você deve garantir que o Servidor do Office Web Apps já está implantado e configurado. Para obter informações sobre o Servidor do Office Web Apps, consulte o artigo [Implantar a infraestrutura: Servidor do Office Online.](https://go.microsoft.com/fwlink/p/?linkid=257525) 
  
Depois que o Servidor do Office Web Apps tiver sido instalado com êxito e seu Web farm estiver configurado corretamente, você deverá configurar o Skype for Business Server para se comunicar com o novo servidor adicionando a URL de descoberta do Servidor do Office Web Apps à sua topologia do Skype for Business Server. 
  
> [!NOTE]
> A iteração mais recente do Servidor do Office Web Apps é chamada servidor do Office Online, que é suportado pelo Skype for Business Server. Para obter mais detalhes, consulte a [documentação do Servidor do Office Online.](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx) 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Configurar o Skype for Business Server para se comunicar com o Servidor do Office Web Apps

Para adicionar o Servidor do Office Web Apps à sua topologia, conclua as seguintes etapas:
  
1. Abra o Construtor de Topologias do Skype for Business Server.
    
2. Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar Topologia da implantação existente** e clique em **OK**.
    
3. Na caixa de diálogo **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.
    
4. No Construtor de Topologias, expanda **o Skype for Business Server,** expanda o nome do seu site, expanda os pools de **front-end** do Enterprise Edition, clique com o botão direito do mouse no nome de um de seus pools e clique em **Editar** Propriedades.
    
5. Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor Office Web Apps** e clique em **Novo** (ou selecione um Servidor Office Web Apps existente na lista suspensa).
    
6. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor Office Web Apps na caixa **FQDN do Servidor Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor Office Web Apps**.
    
   - Se o Servidor do Office Web Apps estiver instalado no local e na mesma zona de rede que o Skype for Business Server, a opção Servidor do Office Web Apps será implantada em uma rede externa **(ou seja, perímetro/Internet)** não deverá ser selecionada.
    
   - Se o Servidor Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.
    
7. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, clique em **OK** e depois em **OK** na caixa de diálogo **Editar Propriedades**. Em seguida, a URL de descoberta será listada como uma das Associações do pool.
    
Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor Office Web Apps.
  
Depois de adicionar a URL de descoberta à topologia, você deve publicar a topologia atualizada. Para isso, no Construtor de Topologias:
  
1. Clique em **Ação** e depois em **Publicar Topologia**.
    
2. No assistente Publicar Topologia, na página **Publicar a topologia**, clique em **Avançar**.
    
3. Na página **Assistente de publicação concluído**, clique em **Concluir**.
    
4. Feche o Construtor de Topologias.
    
## <a name="configure-access-for-external-users"></a>Configurar o acesso para usuários externos

Se você quiser que usuários externos (ou seja, usuários que estejam fazendo logom de fora do firewall da sua organização) tenham acesso às apresentações do PowerPoint do Servidor do Office Web Apps, será necessário usar o Servidor do Office Web Apps e um servidor proxy reverso. Você também precisará criar e configurar uma regra de publicação de site, o que ajudará a garantir que os usuários sejam capazes de se conectar ao servidor. 
  
## <a name="validate-the-configuration"></a>Validar a configuração

Depois que o Servidor do Office Web Apps tiver sido adicionado à topologia e após a publicação dessa topologia, você deverá ver dois novos eventos de log de eventos no log de eventos do Skype for Business Server. Primeiro, um evento LS Data MCU (ID 41034) deve ser adicionado; esse evento relatará que o Servidor do Office Web Apps foi descoberto:
  
 **O Servidor do Office Web Apps do Servidor de Webconferência foi descoberto, o conteúdo do PowerPoint está habilitado.**
  
Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:
  
 **A descoberta do Servidor do Office Web Apps do Servidor de Webconferência foi bem-sucedida.**
  
 **Página interna do apresentador do Servidor do Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**
  
 **Página interna do participante do Servidor do Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**
  
Se você configurou o acesso para usuários externos, também verá algo semelhante a:
  
 **Página do apresentador externo do Servidor do Office Web Apps: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;incorporar**
  
 **Página interna do participante do Servidor do Office Web Apps: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
Se você ver um evento LS Data MCU com o ID 41033, significa que a descoberta do Office Web Apps Server falhou. Nesse caso, o Skype for Business Server tentará quantas vezes for necessário descobrir o Servidor do Office Web Apps recém-configurado. Se o processo de descoberta falhar repetidamente, você deve remover o Office Web Apps Server do seu documento de topologia, publicar a topologia atualizada e tentar adicionar o Office Web Apps Server novamente à topologia depois que os problemas de conectividade tiverem sido resolvidos.
  
Se o Servidor do Office Web Apps parecer estar configurado corretamente e tiver sido reconhecido pelo processo de descoberta, você poderá verificar se o Servidor do Office Web Apps está funcionando conforme o esperado compartilhando uma apresentação do PowerPoint entre um par de clientes do Skype for Business. Se o Usuário A puder carregar e exibir a apresentação do PowerPoint e se o Usuário B puder participar da reunião e ver a apresentação, então o Office Web Apps Server está funcionando.
  
Mesmo que o Servidor do Office Web Apps pareça estar configurado corretamente, você poderia receber a mensagem de erro "Alguns recursos de compartilhamento não estão disponíveis devido a problemas de conectividade do servidor" ao tentar compartilhar uma apresentação do PowerPoint. Se você receber essa mensagem de erro, você deve reiniciar o servidor (ou servidores) de Front End associados ao novo Office Web Apps Server.
  

