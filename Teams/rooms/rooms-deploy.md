---
title: Implantar Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber como implantar salas do Microsoft Teams, incluindo as fases de implantação.
ms.openlocfilehash: 87ded33b464d6f5248fe1fb71d579d5f191bb6b6
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726302"
---
# <a name="deployment-overview"></a>Visão geral de implantação

A implantação das Salas do Microsoft Teams basicamente divide em fases:

- Confirmando que seus locais de implantação (salas) atendem às dependências de implantação
- Criando contas do Microsoft Teams ou skype for Business e exchange e atribuindo-as aos dispositivos de console (consulte [Configure accounts for Microsoft Teams Rooms](rooms-configure-accounts.md))
- Imagens de tablets do Microsoft Surface para funcionar como consoles de Salas do Microsoft Teams (consulte [Configure a Microsoft Teams Rooms console](console.md) or Deploy Microsoft Teams Rooms [mass deployment guide](rooms-scale.md))
- (Opcional) Configurando o Microsoft Operations Management Suite para seus sistemas (consulte [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md)
- Configurando consoles em salas de reunião e conectando os dispositivos periféricos necessários (consulte a documentação do OEM para seu conjunto de dispositivos)

Os técnicos av podem ser usados para a última tarefa, mas o departamento de IT da sua organização precisará fazer as outras partes do processo. 


## <a name="site-readiness"></a>Preparação do site 

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com suas redes e instalações e equipes av para garantir que as dependências de implantação sejam atendidas e que cada site e sala esteja pronto em termos de energia, rede e exibição. Além disso, certifique-se de que os requisitos de instalação física sejam atendidos. Para considerações sobre a instalação física, visite o site do fornecedor e aproveite a experiência da sua equipe av ao instalar e montar telas e executar o cabeamento.

Você pode saber mais sobre essas dependências nos links de orientação de planejamento abaixo:

-   [Verificar a disponibilidade da rede](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Dica pro** - Se você pretende usar servidores proxy para fornecer acesso ao Teams ou Ao Skype for Business Online, primeiro [revise este artigo](../proxy-servers-for-skype-for-business-online.md). Quando se trata de tráfego do Skype for Business em servidores proxy, recomendamos ignorar completamente os servidores proxy. O tráfego do Skype for Business já está criptografado, portanto, os servidores proxy não o tornarão mais seguro. Como parte de sua implantação mais ampla, recomendamos que você siga as diretrizes em Preparar sua rede para o [Teams](../prepare-network.md) para planejamento de largura de banda e avaliação da adequação da sua rede para tráfego em tempo real.

|    |     |
|-----------|------------|
| ![confirmar sites](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos principais requisitos para salas do Microsoft Teams.</li><li>Confirme se você forneceu largura de banda suficiente para cada site.</li></ul>| 
| ![planejar a implantação do dispositivo](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração do dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontidão de serviço

Para se preparar para a implantação das Salas do Microsoft Teams, faça as seguintes tarefas centrais:

-   Defina os recursos da conta de serviço do Microsoft Teams Rooms.
-   Prepare uma unidade organizacional e um grupo do Active Directory para manter suas contas de serviço e máquina do Microsoft Teams Rooms e, opcionalmente, preparar objetos de Política de Grupo (GPOs) para habilitar o remoting do PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir recursos de conta de serviço do Microsoft Teams Rooms 

Dependendo dos cenários de colaboração que você decidiu habilitar com sua implantação de Salas do Microsoft Teams, você precisará determinar os recursos e recursos que você atribui a cada conta de serviço do Microsoft Teams Rooms que você habilitar.

| **Cenário** | **Descrição** | **Recurso de conta de serviço do Microsoft Teams Rooms** |
|---------- |------------- | --- |
| Reuniões interativas            | Usando compartilhamento de voz, vídeo e tela; tornando as Salas do Microsoft Teams um recurso de bookable                     | Habilitado para o Skype for Business, habilitado para o Exchange (Caixa de Correio de Recursos) |
| Conferência discada            | Habilitar reuniões *iniciadas* diretamente do console de Salas do Microsoft Teams com coordenadas de conferência discado | Habilitado para Audioconferência                                          |
| Chamada PSTN de saída/entrada | Habilitar o console de Salas do Microsoft Teams para fazer e receber chamadas PSTN                                         | Habilitado para o Sistema de Telefonia                                                |

Para obter mais informações sobre contas do Microsoft Teams Rooms, consulte [Configure accounts for Microsoft Teams Rooms](rooms-configure-accounts.md).


|    |     |
|-----------|------------|
| ![suporte a cenários](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quais cenários você suportará e identifique os requisitos de licenciamento para suas contas de serviço do Microsoft Teams Rooms.</li></ul>| 
| ![preparar a máquina host](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare-se para hospedar contas de serviço e máquina.</li></ul>| 


_Exemplo da tabela de planejamento de contas de serviço do Microsoft Teams Rooms_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Recursos de sala futuras**                                                 | **Recursos de conta do Microsoft Teams Rooms**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| QG de Londres | Curie         | Média        | 1 tela, áudio e vídeo mais apresentação <br>Acesso de conferência discado<br> Acesso PSTN  | Habilitado para o Skype for Business, habilitado para o Exchange (Caixa de Correio de Recursos) <br>Habilitado para Audioconferência <br>Habilitado para o Sistema de Telefonia |
| QG de Sydney | Monte          | Grande         | 2 Telas, áudio e vídeo mais apresentação<br>Acesso de conferência discado<br> Acesso PSTN  | Habilitado para o Skype for Business, habilitado para o Exchange (Caixa de Correio de Recursos)<br> Habilitado para Audioconferência <br>Habilitado para o Sistema de Telefonia |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Preparar para hospedar contas de serviço e máquina do Microsoft Teams Rooms (opcional)

Para permitir que você gerencie e reporte suas contas de serviço e computador do Microsoft Teams Rooms, prepare o Active Directory local ou o Azure Active Directory (Azure AD). 

Defina um grupo local do Active Directory ou do Azure AD para adicionar todas as contas de serviço (usuário) do Microsoft Teams Rooms e, em seguida, criar relatórios de uso usando o cmdlet Get-CSUserSession PowerShell em sua implantação de Salas do Microsoft Teams. Por exemplo, crie um grupo chamado SkypeRoomSystemsv2-Service-Accounts. 


Defina uma unidade organizacional em sua hierarquia local do Active Directory ou do Azure AD para manter todas as contas de máquina do Microsoft Teams Rooms (se elas ingressarem no domínio) e uma unidade organizacional para manter todas as contas de usuário do Microsoft Teams Rooms. Se você criar uma unidade organizacional para as contas de máquina do Microsoft Teams Rooms, considere desabilitar a herança para garantir que você aplique apenas as políticas que você pretendia aplicar às Salas do Microsoft Teams ingressado no domínio. 

Crie um objeto de Política de Grupo atribuído à unidade da organização que contém suas contas de computador do Microsoft Teams Rooms. Use isso para: 

-   [Definir configurações de conta local e de energia.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Habilitar o Windows Update.
-   Habilitar o remoting do PowerShell. Você pode configurar um script de início para executar um script: Enable-PSRemoting -Force

Você pode usar o PowerShell para executar várias atividades de gerenciamento remoto, incluindo obter e definir informações de configuração. O remoting do PowerShell deve ser habilitado antes que qualquer gerenciamento remoto do PowerShell possa ocorrer e deve ser considerado como parte de seus processos de implantação ou configurado por meio da Política de Grupo.  Para obter mais informações sobre esses recursos e habilita-los, consulte [Maintenance and operations](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuração e implantação 

O planejamento de configuração e implantação abrange as seguintes áreas principais:

-   Provisionamento de conta
-   Instalação de software de dispositivo
-   Implantação de dispositivo
-   Configuração de aplicativo e dispositivo periférico do Microsoft Teams Rooms
-    Testes
-   Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta 

Cada dispositivo de Salas do Microsoft Teams requer uma conta de recurso exclusiva e dedicada que deve ser habilitada para o Microsoft Teams ou o Skype for Business e o Exchange. Essa conta deve ter uma caixa de correio de sala hospedada no Exchange e ser habilitada como uma sala de reunião na implantação do Teams ou do Skype for Business. No lado do Exchange, o processamento de calendário deve ser configurado para que o dispositivo possa aceitar automaticamente solicitações de reunião de entrada. Para obter mais informações sobre como criar essas contas, consulte [Configure accounts for Microsoft Teams Rooms](rooms-configure-accounts.md). 

**Dica pro** – tornar os nomes de exibição dessas contas descritivos e fáceis de entender. Esses são os nomes que os usuários verão ao pesquisar e adicionar sistemas de Salas do Microsoft Teams às reuniões. Algumas organizações usam a convenção *Nome* da Sala de Site ( Capacidade Máxima da Sala )-RS, portanto, por exemplo Curie — uma sala de conferência de 12 pessoas em Londres — pode ter o nome de exibição - LON-CURIE(12)-RS. 

|    |     |
|-----------|------------|
| ![decidir convenção de nomenis](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenis de suas contas do Microsoft Teams Rooms.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>| 
| ![próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalação de software de dispositivo 

Ao planejar a implantação das Salas do Microsoft Teams, você tem muitas opções a considerar para instalar o software necessário. Cenários e abordagens comuns são descritos na tabela a seguir. 

| **Cenário**            | **Abordagem**         |
|-------------------------|-----------------------|   
|Implantando alguns dispositivos do Microsoft Teams Rooms (<10). | Se estiver usando salas do Microsoft Teams baseadas no Surface Pro, siga as instruções de instalação [para uma instalação por dispositivo.](console.md) [Este vídeo prático orienta você durante o processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se estiver usando uma solução integrada, implante usando a imagem do fornecedor e configure as configurações conforme necessário. |
| Implantação entre 10 e 50 dispositivos de um único fornecedor.     | Crie uma imagem baseada em WIM, pause após a etapa [6](console.md)na orientação e capture uma imagem de distribuição a ser usada com sua tecnologia de distribuição de clonagem.    |
| Implantando mais de 50 dispositivos do Microsoft Teams Rooms, implantando dispositivos de mais de um fornecedor ou exigindo agentes específicos da organização como parte da implantação. | Use uma plataforma de com build e distribuição de software baseada em sequência de tarefas, como [o Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Dica pro** - Cada Sala do Microsoft Teams deve ter um nome de máquina válido e exclusivo em sua rede. Muitos sistemas de monitoramento e alerta exibem o nome do computador como um identificador de chave, portanto, é importante desenvolver uma convenção de nomenização para implantações de Salas do Microsoft Teams que permite que a equipe de suporte localize facilmente as Salas do Microsoft Teams que foram sinalizadas como exigindo uma ação. Um exemplo pode estar usando um padrão de MTR-*Site* - *Room Name* (MTR-LON-CURIE). 

Como parte da implantação, você também precisará considerar sua estratégia para gerenciar e configurar as contas [locais](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) criadas pelo instalador de aplicativos do Microsoft Teams Rooms.

Fornecemos orientações sobre como usar o [Microsoft Azure Monitor](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para monitorar a implantação das Salas do Microsoft Teams e relatar a disponibilidade, erros de hardware/software e a versão do aplicativo salas do Microsoft Teams. Se você decidir usar o Microsoft Operations Management Suite, instale o agente do Operations Management Suite como parte do processo de instalação de software e configure as informações de conexão de espaço de trabalho para seu espaço de trabalho. 

Uma consideração adicional é se as Salas do Microsoft Teams serão ingressada no domínio. Informações sobre os benefícios da junção de domínio podem ser encontradas em Considerações de junção de domínio do Sistema de Sala [do Skype.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![nomenis de dispositivo de pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomeação de dispositivo do Microsoft Teams Rooms a ser usada durante sua implantação.</li><li>Decida se você ingressará em dispositivos do Microsoft Teams Rooms em seu domínio e como gerenciar e configurar contas locais. </li><li>Decida se você usará o Operations Management Suite para monitorar a implantação das Salas do Microsoft Teams.</li><li>Decida qual método você usará para implantar o software e os agentes no sistema salas do Microsoft Teams em preparação para a implantação do dispositivo. </li></ul>| 
| ![próximos passos planejar dispositivo](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar sua abordagem de implantação de dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implantação de dispositivo

Depois de ter implantado seu software para as unidades do Microsoft Teams Rooms, crie seu plano para enviar os dispositivos e seus dispositivos periféricos atribuídos para suas salas e, em seguida, prossiga para instalação e configuração. 


|    |     |
|-----------|------------|
| ![gerenciar a implantação site a site](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação site a site.</li><li> Identifique os recursos que instalarão os dispositivos do Microsoft Teams Rooms no site e realizarão a configuração e o teste.</li></ul>| 
| ![iniciar teste de dispositivo](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste do dispositivo.</li></ul>| 

_Tabela de implantação de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Sistema de Salas do Microsoft Teams**  | **Dispositivos periféricos**  | **Nome do computador salas do Microsoft Teams**  | **Conta de recurso salas do Microsoft Teams**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| QG de Londres | Curie         | Média        |                                   |                  |                                          |                                             |
| QG de Sydney | Monte          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configuração de aplicativo e dispositivo periférico do Microsoft Teams Rooms 

Depois que cada sistema de Salas do Microsoft Teams tiver sido implantado fisicamente e os dispositivos periféricos com suporte conectados, você precisará configurar o aplicativo Salas do Microsoft Teams para atribuir a conta de recurso e senha do Microsoft Teams Rooms criada anteriormente, para permitir que o sistema de Salas do Microsoft Teams entre no Microsoft Teams ou skype for Business e exchange. É fundamental aproveitar periféricos de áudio e vídeo USB certificados vinculados em outro lugar do documento. Não fazer isso pode resultar em comportamento imprevisível. 

Você pode configurar manualmente cada sistema de Salas do Microsoft Teams. Como alternativa, você pode usar um arquivo de configuração XML de Salas do Microsoft Teams armazenado centralmente para gerenciar as configurações do aplicativo e aproveitar um script GPO de inicialização para reaplicar a configuração que você deseja, sempre que o sistema salas do Microsoft Teams for inicializado. 

Para obter mais informações sobre como usar o arquivo de configuração XML, consulte [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md). 

Você pode usar [o PowerShell remoto](rooms-operations.md#remote-management-using-powershell) para puxar a configuração de Salas do Microsoft Teams para necessidades de relatórios. 

|    |     |
|-----------|------------|
| ![configurar ponto de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se você configurará manualmente cada sistema de Salas do Microsoft Teams ou usará um arquivo XML central (um por dispositivo de Salas do Microsoft Teams).</li></ul>| 
| ![próximas etapas abordagem remota](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua abordagem de gerenciamento remoto.</li></ul>| 

### <a name="testing"></a> Testes

Depois que o sistema de Salas do Microsoft Teams tiver sido implantado, você deve testá-lo. Verifique se os recursos listados nas Salas do [Microsoft Teams estão](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funcionando no dispositivo implantado. É altamente recomendável que a equipe de implantação verifique se as Salas do Microsoft Teams estão fazendo logons no Microsoft Operations Management Suite (se usado). Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade. Para obter mais informações, consulte esta [lista de verificação de implantação útil.](console.md#microsoft-teams-rooms-deployment-checklist)

Recomendamos que, como parte da avaliação geral do Teams ou do Skype for Business, você configure a criação de arquivos para o Painel de Qualidade de Chamadas (CQD), monitore tendências de qualidade e participe do processo de Revisão da Qualidade da Experiência. Para obter mais informações, consulte [Improve and monitor call quality for Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você deseja atualizar seu registro de ativos com o nome da sala, o nome do dispositivo do Microsoft Teams Rooms, a conta de recurso de Salas do Microsoft Teams conectado e os dispositivos periféricos atribuídos (e quais portas USB eles usam). 

_Tabela de ativos de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Microsoft Teams Rooms serial no.**  | **Dispositivos periféricos/ Não serial./ Portas**  | **Nome do computador salas do Microsoft Teams**  | **Conta de serviço do Microsoft Teams Rooms**  | **Data implantada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| QG de Londres | Curie         | Média        |                                          |                                          |                                          |                                            |                   |
| QG de Sydney | Monte          | Grande         |                                          |                                          |                                          |                                            |                   |


