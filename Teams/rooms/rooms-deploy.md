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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber como implantar Salas do Microsoft Teams, incluindo as fases de implantação.
ms.openlocfilehash: 3c7420880bd36d1ebacd778d623da14e1705e324
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730400"
---
# <a name="deployment-overview"></a>Visão geral de implantação

A implantação Salas do Microsoft Teams basicamente se divide em fases:

- Confirmando que seus locais de implantação (salas) atendem às dependências de implantação
- Criando Microsoft Teams ou Skype for Business contas Exchange e atribuindo-as aos dispositivos de console (consulte [Configure accounts for Salas do Microsoft Teams](rooms-configure-accounts.md))
- Imagens de tablets do Microsoft Surface para funcionarem como consoles Salas do Microsoft Teams (consulte [Configure a Salas do Microsoft Teams console](console.md) ou Deploy Salas do Microsoft Teams [mass deployment guide](rooms-scale.md))
- (Opcional) Configurando o Microsoft Operations Management Suite para seus sistemas (consulte [Deploy Salas do Microsoft Teams management with Azure Monitor](azure-monitor-deploy.md)
- Configurando consoles em salas de reunião e conectando os dispositivos periféricos necessários (consulte a documentação do OEM para seu conjunto de dispositivos)

Os técnicos av podem ser usados para a última tarefa, mas o departamento de IT da sua organização precisará fazer as outras partes do processo. 


## <a name="site-readiness"></a>Preparação do site 

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com suas redes e instalações e equipes av para garantir que as dependências de implantação sejam atendidas e que cada site e sala esteja pronto em termos de energia, rede e exibição. Além disso, certifique-se de que os requisitos de instalação física sejam atendidos. Para considerações sobre a instalação física, visite o site do fornecedor e aproveite a experiência da sua equipe av ao instalar e montar telas e executar o cabeamento.

Você pode saber mais sobre essas dependências nos links de orientação de planejamento abaixo:

-   [Verificar a disponibilidade da rede](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro Dica** - Se você pretende usar servidores proxy para fornecer acesso ao Teams ou Skype for Business Online, primeiro [revise este artigo](../proxy-servers-for-skype-for-business-online.md). Quando se trata de Skype for Business tráfego por servidores proxy, recomendamos ignorar completamente os servidores proxy. Skype for Business o tráfego já está criptografado, portanto, os servidores proxy não o tornarão mais seguro. Como parte de sua implantação mais ampla, recomendamos que você siga as diretrizes em [Preparar](../prepare-network.md) sua rede para o Teams para planejamento de largura de banda e avaliação da adequação da sua rede para tráfego em tempo real.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confirme sites.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos principais requisitos para Salas do Microsoft Teams.</li><li>Confirme se você forneceu largura de banda suficiente para cada site.</li></ul>| 
| ![planejar a implantação do dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração do dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontidão de serviço

Para se preparar para sua implantação Salas do Microsoft Teams, faça as seguintes tarefas centrais:

-   Defina Salas do Microsoft Teams de conta de serviço.
-   Prepare uma unidade organizacional e um grupo do Active Directory para manter suas contas de serviço e de máquina Salas do Microsoft Teams e, opcionalmente, preparar objetos de Política de Grupo (GPOs) para habilitar o remoting do PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir Salas do Microsoft Teams de conta de serviço 

Dependendo dos cenários de colaboração que você decidiu habilitar com Salas do Microsoft Teams implantação do Salas do Microsoft Teams, você precisará determinar os recursos e recursos que você atribui a cada conta de serviço Salas do Microsoft Teams que você habilitar.

| **Cenário** | **Descrição** | **Salas do Microsoft Teams de conta de serviço** |
|---------- |------------- | --- |
| Reuniões interativas            | Usando compartilhamento de voz, vídeo e tela; tornando a Salas do Microsoft Teams um recurso bookable                     | Habilitado para Skype for Business, habilitado para Exchange (Caixa de Correio de Recursos) |
| Conferência discada            | Habilitar reuniões *iniciadas* diretamente do console Salas do Microsoft Teams com coordenadas de conferência discado | Habilitado para Audioconferência                                          |
| Chamada PSTN de saída/entrada | Habilitar Salas do Microsoft Teams console para fazer e receber chamadas PSTN                                         | Habilitado para Sistema de Telefonia                                                |

Para obter mais informações sobre Salas do Microsoft Teams contas, consulte [Configure accounts for Salas do Microsoft Teams](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![suporte a cenários.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quais cenários você vai dar suporte e identifique os requisitos de licenciamento para suas contas Salas do Microsoft Teams de serviço.</li></ul>| 
| ![preparar a máquina host.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare-se para hospedar contas de serviço e máquina.</li></ul>| 


_Exemplo Salas do Microsoft Teams de planejamento de conta de serviço_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Recursos de sala futuras**                                                 | **Salas do Microsoft Teams de conta**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| QG de Londres | Curie         | Média        | 1 tela, áudio e vídeo mais apresentação <br>Acesso de conferência discado<br> Acesso PSTN  | Habilitado para Skype for Business, habilitado para Exchange (Caixa de Correio de Recursos) <br>Habilitado para Audioconferência <br>Habilitado para Sistema de Telefonia |
| QG de Sydney | Monte          | Grande         | 2 Telas, áudio e vídeo mais apresentação<br>Acesso de conferência discado<br> Acesso PSTN  | Habilitado para Skype for Business, habilitado para Exchange (Caixa de Correio de Recursos)<br> Habilitado para Audioconferência <br>Habilitado para Sistema de Telefonia |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Preparar para hospedar Salas do Microsoft Teams de máquina e serviço (opcional)

Para permitir que você gerencie e reporte suas contas de serviço e de computador Salas do Microsoft Teams, prepare o Active Directory local ou o Azure Active Directory (Azure AD). 

Defina um grupo local do Active Directory ou do Azure AD para adicionar todas as contas de serviço do Salas do Microsoft Teams (usuário) e, em seguida, criar relatórios de uso usando o cmdlet do Get-CSUserSession PowerShell em sua implantação Salas do Microsoft Teams do Salas do Microsoft Teams. Por exemplo, crie um grupo chamado SkypeRoomSystemsv2-Service-Accounts. 


Defina uma unidade organizacional em sua hierarquia local do Active Directory ou do Azure AD para manter todas as contas de máquina Salas do Microsoft Teams (se elas ingressarem no domínio) e uma unidade organizacional para manter todas as contas de usuário Salas do Microsoft Teams de usuário. Se você criar uma unidade organizacional para as contas de máquina Salas do Microsoft Teams, considere desabilitar a herança para garantir que você aplique apenas as políticas que você pretendia aplicar ao domínio ingressado no Salas do Microsoft Teams. 

Crie um objeto de Política de Grupo atribuído à unidade da organização que contém suas Salas do Microsoft Teams de computador. Use isso para: 

-   [Definir configurações de conta local e de energia.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Habilitar Windows Update.
-   Habilitar o remoting do PowerShell. Você pode configurar um script de início para executar um script: Enable-PSRemoting -Force

Você pode usar o PowerShell para executar várias atividades de gerenciamento remoto, incluindo obter e definir informações de configuração. O remoting do PowerShell deve ser habilitado antes que qualquer gerenciamento remoto do PowerShell possa ocorrer e deve ser considerado como parte de seus processos de implantação ou configurado por meio da Política de Grupo.  Para obter mais informações sobre esses recursos e habilita-los, consulte [Maintenance and operations](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuração e implantação 

O planejamento de configuração e implantação abrange as seguintes áreas principais:

-   Provisionamento de conta
-   Instalação de software de dispositivo
-   Implantação de dispositivo
-   Salas do Microsoft Teams aplicativo e configuração de dispositivo periférico
-    Testes
-   Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta 

Cada Salas do Microsoft Teams requer uma conta de recurso exclusiva e dedicada que deve ser habilitada para Microsoft Teams ou Skype for Business e Exchange. Essa conta deve ter uma caixa de correio de sala hospedada no Exchange e ser habilitada como uma sala de reunião na Teams ou Skype for Business implantação. No lado Exchange, o processamento de calendário deve ser configurado para que o dispositivo possa aceitar automaticamente solicitações de reunião de entrada. Para obter mais informações sobre como criar essas contas, consulte [Configure accounts for Salas do Microsoft Teams](rooms-configure-accounts.md). 

**Pro Dica** – Tornar os nomes de exibição dessas contas descritivos e fáceis de entender. Esses são os nomes que os usuários verão ao pesquisar e adicionar Salas do Microsoft Teams a reuniões. Algumas organizações usam a convenção *Nome* da Sala de Site ( Capacidade Máxima da Sala )-RS, portanto, por exemplo Curie — uma sala de conferência de 12 pessoas em Londres — pode ter o nome de exibição - LON-CURIE(12)-RS. 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![decidir a convenção de nomenis.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenissão para suas Salas do Microsoft Teams contas.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>| 
| ![próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalação de software de dispositivo 

Ao planejar a implantação Salas do Microsoft Teams, você tem muitas opções a considerar para instalar o software necessário. Cenários e abordagens comuns são descritos na tabela a seguir. 

| **Cenário**            | **Abordagem**         |
|-------------------------|-----------------------|   
|Implantando alguns dispositivos Salas do Microsoft Teams (<10). | Se usar Surface Pro de Salas do Microsoft Teams, siga as instruções de [instalação para uma instalação por dispositivo.](console.md) [Este vídeo prático orienta você durante o processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se estiver usando uma solução integrada, implante usando a imagem do fornecedor e configure as configurações conforme necessário. |
| Implantação entre 10 e 50 dispositivos de um único fornecedor.     | Crie uma imagem baseada em WIM, pause após a etapa [6](console.md)na orientação e capture uma imagem de distribuição a ser usada com sua tecnologia de distribuição de clonagem.    |
| Implantando mais de 50 Salas do Microsoft Teams dispositivos, implantando dispositivos de mais de um fornecedor ou exigindo agentes específicos da organização como parte da implantação. | Use uma plataforma de com build e distribuição de software baseada em sequência de [tarefas,](rooms-scale.md)como Microsoft Endpoint Configuration Manager .  |


**Pro Dica** - Cada Salas do Microsoft Teams deve ter um nome de máquina válido e exclusivo em sua rede. Muitos sistemas de monitoramento e alerta exibem o nome do computador como um identificador de chave, portanto, é importante desenvolver uma convenção de nomenização para implantações do Salas do Microsoft Teams que permite que a equipe de suporte localize facilmente o Salas do Microsoft Teams que foi sinalizado como exigindo uma ação. Um exemplo pode estar usando um padrão de MTR-*Site* - *Room Name* (MTR-LON-CURIE). 

Como parte da implantação, você também precisará considerar sua estratégia para gerenciar e configurar as contas [locais](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) criadas pelo Salas do Microsoft Teams de aplicativos.

Fornecemos orientações sobre como usar o [monitor Microsoft Azure](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para monitorar Salas do Microsoft Teams implantação e relatório sobre disponibilidade, erros de hardware/software e Salas do Microsoft Teams versão do aplicativo. Se você decidir usar o Microsoft Operations Management Suite, instale o agente do Operations Management Suite como parte do processo de instalação de software e configure as informações de conexão de espaço de trabalho para seu espaço de trabalho. 

Uma consideração adicional é se o Salas do Microsoft Teams será ingressado no domínio. As informações sobre os benefícios da junção de domínio podem ser encontradas Skype considerações de junção de domínio do Sistema de [Sala.](domain-joining-considerations.md) 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![nomenis de dispositivo de pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a Salas do Microsoft Teams de nomenisagem de dispositivo a ser usada durante a implantação.</li><li>Decida se você ingressará Salas do Microsoft Teams dispositivos no seu domínio e como gerenciar e configurar contas locais. </li><li>Decida se você usará o Operations Management Suite para monitorar a Salas do Microsoft Teams implantação.</li><li>Decida qual método você usará para implantar o software e os agentes no sistema Salas do Microsoft Teams em preparação para a implantação do dispositivo. </li></ul>| 
| ![próximas etapas planejam o dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar sua abordagem de implantação de dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implantação de dispositivo

Depois de ter implantado seu software para as unidades Salas do Microsoft Teams, crie seu plano para enviar os dispositivos e seus dispositivos periféricos atribuídos para suas salas e, em seguida, prossiga para instalação e configuração. 


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![gerenciar a implantação site a site.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação site a site.</li><li> Identifique os recursos que instalarão os dispositivos Salas do Microsoft Teams no site e realizar a configuração e o teste.</li></ul>| 
| ![iniciar o teste do dispositivo.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste do dispositivo.</li></ul>| 

_Tabela de implantação de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Salas do Microsoft Teams sistema**  | **Dispositivos periféricos**  | **Salas do Microsoft Teams nome do computador**  | **Salas do Microsoft Teams de recurso**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| QG de Londres | Curie         | Média        |                                   |                  |                                          |                                             |
| QG de Sydney | Monte          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Salas do Microsoft Teams aplicativo e configuração de dispositivo periférico 

Depois que cada sistema Salas do Microsoft Teams tiver sido implantado fisicamente e os dispositivos periféricos com suporte conectados, você precisará configurar o aplicativo Salas do Microsoft Teams para atribuir a conta de recurso do Salas do Microsoft Teams e a senha criadas anteriormente, para permitir que o sistema Salas do Microsoft Teams entre no Microsoft Teams ou Skype for Business e Exchange. É fundamental aproveitar periféricos de áudio e vídeo USB certificados vinculados em outro lugar do documento. Não fazer isso pode resultar em comportamento imprevisível. 

Você pode configurar manualmente cada Salas do Microsoft Teams sistema. Como alternativa, você pode usar um arquivo de configuração XML armazenado centralmente por Salas do Microsoft Teams para gerenciar as configurações do aplicativo e aproveitar um script GPO de inicialização para reaplicar a configuração que você deseja, sempre que o sistema Salas do Microsoft Teams inicializar. 

Para obter mais informações sobre como usar o arquivo de configuração XML, consulte [Manage a Salas do Microsoft Teams console settings remotely with an XML configuration file](xml-config-file.md). 

Você pode usar [o PowerShell remoto](rooms-operations.md#remote-management-using-powershell) para puxar a configuração Salas do Microsoft Teams para necessidades de relatórios. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configuração do ponto de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se você configurará manualmente cada sistema Salas do Microsoft Teams ou usará um arquivo XML central (um por Salas do Microsoft Teams dispositivo).</li></ul>| 
| ![próximas etapas de abordagem remota.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua abordagem de gerenciamento remoto.</li></ul>| 

### <a name="testing"></a> Testes

Depois que Salas do Microsoft Teams sistema de segurança tiver sido implantado, você deve testá-lo. Verifique se os recursos listados [Salas do Microsoft Teams ajuda estão](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funcionando no dispositivo implantado. É altamente recomendável que a equipe de implantação verifique se o Salas do Microsoft Teams está fazendo logo em log no Microsoft Operations Management Suite (se usado). Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade. Para obter mais informações, consulte esta [lista de verificação de implantação útil.](console.md#microsoft-teams-rooms-deployment-checklist)

Recomendamos que, como parte da Teams ou Skype for Business, você configure a criação de arquivos para o CQD (Painel de Qualidade de Chamada), monitore tendências de qualidade e participe do processo de Revisão da Qualidade da Experiência. Para obter mais informações, consulte [Improve and monitor call quality for Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você vai querer atualizar seu registro de ativo com o nome da sala, o nome do dispositivo Salas do Microsoft Teams, a conta de recurso de entrada Salas do Microsoft Teams e os dispositivos periféricos atribuídos (e quais portas USB eles usam). 

_Tabela de ativos de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Salas do Microsoft Teams serial no.**  | **Dispositivos periféricos/ Não serial./ Portas**  | **Salas do Microsoft Teams nome do computador**  | **Salas do Microsoft Teams de serviço**  | **Data implantada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| QG de Londres | Curie         | Média        |                                          |                                          |                                          |                                            |                   |
| QG de Sydney | Monte          | Grande         |                                          |                                          |                                          |                                            |                   |