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
description: Leia este artigo para saber mais sobre como implantar salas do Microsoft Teams, incluindo as fases de implantação.
ms.openlocfilehash: 53c4c94717f10dadbad802cff3f233a3a771d166
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662246"
---
# <a name="deployment-overview"></a>Visão geral de implantação

A implantação das Salas do Microsoft Teams basicamente se divide em fases:

- Confirmando que seus locais de implantação (salas) atendem às dependências de implantação
- Criando contas do Microsoft Teams ou Skype for Business e Exchange e atribuindo-as aos dispositivos de console (consulte Configurar contas para Salas [do Microsoft Teams)](rooms-configure-accounts.md)
- Imagem de tablets Do Microsoft Surface para funcionar como consoles de Salas do Microsoft Teams (consulte Configurar um console de Salas do [Microsoft Teams](console.md) ou Implantar o guia de implantação em massa de Salas do Microsoft [Teams)](rooms-scale.md)
- (Opcional) Configurando o Pacote de Gerenciamento de Operações da Microsoft para seus sistemas (consulte Implantar o gerenciamento de Salas [do Microsoft Teams com o Monitor do Azure](azure-monitor-deploy.md)
- Configurando consoles em salas de reunião e conectando os dispositivos periféricos necessários (consulte a documentação OEM para seu conjunto de dispositivos)

Os técnicos av podem ser usados para a última tarefa, mas o departamento de EQUIPE da sua organização precisará fazer as outras partes do processo. 


## <a name="site-readiness"></a>Preparação do site 

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com suas instalações de rede e equipes av para garantir que as dependências de implantação sejam atendidas e que cada site e sala esteja pronto em termos de energia, rede e exibição. Além disso, certifique-se de que os requisitos de instalação física sejam atendidos. Para considerações sobre a instalação física, visite o site do fornecedor e aproveite a experiência da sua equipe av ao instalar e instalar telas e executar o cabeamento.

Você pode saber mais sobre essas dependências nos links de orientação de planejamento abaixo:

-   [Verificar a disponibilidade da rede](rooms-prep.md#check-network-availability)
-   [Certificados](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Dica profissional** - Se você pretende usar servidores proxy para fornecer acesso ao Teams ou ao Skype for Business Online, primeiro [revise este artigo.](../proxy-servers-for-skype-for-business-online.md) Observe que, quando se trata de tráfego do Skype for Business em servidores proxy, recomendamos ignorar completamente os servidores proxy. O tráfego do Skype for Business já está criptografado, portanto os servidores proxy não o tornarão mais seguro. Como parte de sua implantação mais ampla, recomendamos que você siga as orientações em Preparar sua rede para o [Teams](../prepare-network.md) para planejamento de largura de banda e avaliação da adequação da rede para o tráfego em tempo real.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos principais requisitos para salas do Microsoft Teams.</li><li>Confirme que você forneceu largura de banda suficiente para cada site.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração do dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontidão de serviço

Para se preparar para a implantação das Salas do Microsoft Teams, faça o seguinte:

-   Defina os recursos da conta de serviço salas do Microsoft Teams.
-   Prepare uma unidade organizacional e um grupo do Active Directory para manter suas contas de máquina e serviço de Salas do Microsoft Teams e, opcionalmente, preparar objetos de Política de Grupo (GPOs) para habilitar a remoção do PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir recursos de conta de serviço salas do Microsoft Teams 

Dependendo dos cenários de colaboração que você decidiu habilitar com a implantação de Salas do Microsoft Teams, será necessário determinar os recursos e recursos atribuídos a cada conta de serviço de Salas do Microsoft Teams que você habilitar.

| **Cenário** | **Descrição** | **Recurso de conta de serviço salas do Microsoft Teams** |
|---------- |------------- | --- |
| Reuniões interativas            | Usando o compartilhamento de voz, vídeo e tela; tornando as Salas do Microsoft Teams um recurso a ser reservado                     | Habilitado para o Skype for Business, habilitado para o Exchange (Caixa de Correio de Recursos) |
| Conferência discada            | Habilitar reuniões *iniciadas* diretamente do console salas do Microsoft Teams com coordenadas de conferência discda | Habilitado para Audioconferência                                          |
| Chamada PSTN de saída/entrada | Habilitar o console salas do Microsoft Teams para fazer e receber chamadas PSTN                                         | Habilitado para o Sistema de Telefonia                                                |

Para obter mais informações sobre contas de Salas do Microsoft Teams, consulte [Configurar contas para Salas do Microsoft Teams.](rooms-configure-accounts.md)


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quais cenários você terá suporte e identifique requisitos de licenciamento para suas contas de serviço de Salas do Microsoft Teams.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare-se para hospedar contas de máquina e serviço.</li></ul>| 


_Exemplo de tabela de planejamento de conta de serviço salas do Microsoft Teams_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Recursos futuros da sala**                                                 | **Recursos de conta do Microsoft Teams Rooms**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Curie         | Média        | 1 tela, áudio e vídeo mais apresentação <br>Acesso à conferência discado<br> Acesso PSTN  | Habilitado para o Skype for Business, habilitado para o Exchange (Caixa de Correio de Recursos) <br>Habilitado para Audioconferência <br>Habilitado para o Sistema de Telefonia |
| Sydney HQ | Hill          | Grande         | 2 Telas, áudio e vídeo mais apresentação<br>Acesso à conferência discado<br> Acesso PSTN  | Habilitado para o Skype for Business, habilitado para o Exchange (Caixa de Correio de Recursos)<br> Habilitado para Audioconferência <br>Habilitado para o Sistema de Telefonia |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Preparar-se para hospedar contas de máquina e serviço do Microsoft Teams Rooms (opcional)

Para permitir que você gerencie e reporte suas contas de máquina e serviço do Microsoft Teams Rooms, prepare o Active Directory local ou o Azure Active Directory (Azure AD). 

Defina um grupo local do Active Directory ou do Azure AD para adicionar todas as contas de serviço (usuário) do Microsoft Teams Rooms e, em seguida, crie relatórios de uso usando o cmdlet Get-CSUserSession PowerShell em sua implantação de Salas do Microsoft Teams. Por exemplo, crie um grupo chamado SkypeRoomSystemsv2-Service-Accounts. 


Defina uma unidade organizacional em sua hierarquia local do Active Directory ou do Azure AD para manter todas as contas de computador do Microsoft Teams Rooms (se elas ingressarem no domínio) e uma unidade organizacional para manter todas as contas de usuário de Salas do Microsoft Teams. Se você criar uma unidade organizacional para as contas de computador do Microsoft Teams Rooms, considere desabilitar a herança para garantir que você aplique apenas as políticas que pretende aplicar às Salas do Microsoft Teams unidas pelo domínio. 

Crie um objeto de Política de Grupo atribuído à unidade da organização que contenha suas contas de computador salas do Microsoft Teams. Use isto para: 

-   [Definir configurações de energia e conta local.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Habilitar o Windows Update.
-   Habilitar a remoção do PowerShell. Você pode configurar um script de início para executar um script simples: Enable-PSRemoting -Force

Você pode usar o PowerShell para executar várias atividades de gerenciamento remoto, incluindo obter e definir informações de configuração. A remoção do PowerShell deve ser habilitada para que qualquer gerenciamento remoto do PowerShell possa ocorrer e deve ser considerada como parte de seus processos de implantação ou configurada por meio da Política de Grupo.  Para obter mais informações sobre esses recursos e habilita-los, consulte [Manutenção e operações.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Configuração e implantação 

O planejamento de configuração e implantação abrange as seguintes áreas principais:

-   Provisionamento de conta
-   Instalação de software de dispositivo
-   Implantação de dispositivo
-   Aplicativo Salas do Microsoft Teams e configuração de dispositivo periférico
-    Testes
-   Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta 

Cada dispositivo do Microsoft Teams Rooms requer uma conta de recurso exclusiva e dedicada que deve ser habilitada para o Microsoft Teams ou o Skype for Business e o Exchange. Essa conta deve ter uma caixa de correio de sala hospedada no Exchange e ser habilitada como uma sala de reunião na implantação do Teams ou do Skype for Business. No lado do Exchange, o processamento do calendário deve ser configurado para que o dispositivo possa aceitar automaticamente solicitações de reunião recebidas. Para obter mais informações sobre como criar essas contas, consulte [Configurar contas para Salas do Microsoft Teams.](rooms-configure-accounts.md) 

**Dica profissional** – tornar os nomes de exibição dessas contas descritivos e fáceis de entender. Esses são os nomes que os usuários verão ao pesquisar e adicionar sistemas de Salas do Microsoft Teams às reuniões. Algumas organizações usam a convenção *Nome* da Sala do Site ( Capacidade Máxima da Sala )-RS, portanto, Curie (uma sala de conferência de 12 pessoas em Londres) pode ter o nome de exibição - LON-CURIE(12)-RS. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenu das suas contas de Salas do Microsoft Teams.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalação de software de dispositivo 

Ao planejar a implantação de Salas do Microsoft Teams, você tem várias opções a considerar para instalar o software necessário. Cenários e abordagens comuns são descritos na tabela a seguir. 

| **Cenário**            | **Abordagem**         |
|-------------------------|-----------------------|   
|Implantando um pequeno número de dispositivos de Salas do Microsoft Teams (<10). | Se estiver usando salas do Microsoft Teams baseadas no Surface Pro, siga as instruções de instalação [de uma instalação por dispositivo.](console.md) [Este vídeo útil orienta você durante o processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se estiver usando uma solução integrada, implante usando a imagem do fornecedor e configure as configurações conforme necessário. |
| Implantação entre 10 e 50 dispositivos de um único fornecedor.     | Crie uma imagem baseada em WIM, pause após a etapa [6](console.md)na orientação e capture uma imagem de distribuição a ser usada com sua tecnologia de distribuição de clonagem.    |
| Implantando mais de 50 dispositivos de Salas do Microsoft Teams, implantando dispositivos de mais de um fornecedor ou exigindo agentes específicos da organização como parte da implantação. | Use uma plataforma de distribuição e com build de software baseado em sequência de tarefas, como [o Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Dica profissional** : cada Sala do Microsoft Teams deve ter um nome de máquina válido e exclusivo em sua rede. Muitos sistemas de monitoramento e alerta exibem o nome do computador como um identificador-chave, portanto, é importante desenvolver uma convenção de nomenculação para implantações de Salas do Microsoft Teams que permite ao pessoal de suporte localizar facilmente as Salas do Microsoft Teams que foram sinalizadas como solicitando uma ação. Um exemplo pode estar usando um padrão de MTR-*Nome* da Sala do Site -  (MTR-LON-CURIE). 

Como parte da implantação, você também precisará considerar sua estratégia [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) para gerenciar e configurar as contas locais criadas pelo instalador de aplicativos Salas do Microsoft Teams.

Fornecemos orientações sobre como usar o Monitor do [Microsoft Azure](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para monitorar a implantação de Salas do Microsoft Teams e relatar a disponibilidade, erros de hardware/software e a versão do aplicativo Salas do Microsoft Teams. Se você decidir usar o Pacote de Gerenciamento de Operações da Microsoft, deverá instalar o agente do Pacote de Gerenciamento de Operações como parte do processo de instalação de software e configurar as informações de conexão do espaço de trabalho para o seu espaço de trabalho. 

Uma consideração adicional é se as Salas do Microsoft Teams serão unidas pelo domínio. Informações sobre os benefícios da junção de domínio podem ser encontradas nas considerações de junção de domínios [do Skype Room System.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenuidade de dispositivos do Microsoft Teams Rooms a ser usada durante sua implantação.</li><li>Decida se você ingressará em dispositivos do Microsoft Teams Rooms em seu domínio e como gerenciar e configurar contas locais. </li><li>Decida se você usará o Pacote de Gerenciamento de Operações para monitorar a implantação das Salas do Microsoft Teams.</li><li>Decida qual método você usará para implantar o software e os agentes no sistema salas do Microsoft Teams em preparação para a implantação do dispositivo. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a abordagem de implantação do dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implantação de dispositivo

Depois de ter implantado seu software nas unidades de Salas do Microsoft Teams, crie seu plano para enviar os dispositivos e seus dispositivos periféricos atribuídos para suas salas e, em seguida, prossiga para a instalação e configuração. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação local por site.</li><li> Identifique os recursos que instalarão os dispositivos de Salas do Microsoft Teams no local e realizar a configuração e os testes.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste do dispositivo.</li></ul>| 

_Exemplo de tabela de implantação_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Sistema salas do Microsoft Teams**  | **Dispositivos periféricos**  | **Nome do computador salas do Microsoft Teams**  | **Conta de recurso salas do Microsoft Teams**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Curie         | Média        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Aplicativo Salas do Microsoft Teams e configuração de dispositivo periférico 

Depois que cada sistema de Salas do Microsoft Teams tiver sido implantado fisicamente e os dispositivos periféricos compatíveis conectados, você precisará configurar o aplicativo Salas do Microsoft Teams para atribuir a conta de recurso Salas do Microsoft Teams e a senha criadas anteriormente, para permitir que o sistema de Salas do Microsoft Teams entre no Microsoft Teams ou no Skype for Business e no Exchange. É fundamental aproveitar periféricos de áudio e vídeo USB certificados vinculados em outro lugar do documento. Não fazer isso pode resultar em comportamento imprevisível. 

Você pode configurar manualmente cada sistema de Salas do Microsoft Teams. Como alternativa, você pode usar um arquivo de configuração XML de Salas do Microsoft Teams armazenado centralmente para gerenciar as configurações do aplicativo e aproveitar um script DE GPO de inicialização para reaplicar a configuração que você deseja, sempre que o sistema salas do Microsoft Teams for inicializado. 

Para obter mais informações sobre como usar o arquivo de configuração XML, consulte Gerenciar remotamente as configurações de um console de Salas do [Microsoft Teams com um arquivo de configuração XML.](xml-config-file.md) 

Você pode usar [o PowerShell remoto para](rooms-operations.md#remote-management-using-powershell) usar a configuração de Salas do Microsoft Teams para necessidades de geração de relatórios. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se você configurará manualmente cada sistema de Salas do Microsoft Teams ou usará um arquivo XML central (um por dispositivo de Salas do Microsoft Teams).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua abordagem de gerenciamento remoto.</li></ul>| 

### <a name="testing"></a> Testes

Depois que o sistema salas do Microsoft Teams tiver sido implantado, você deverá testá-lo. Verifique se os recursos listados nas [Salas do Microsoft Teams estão](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) funcionando no dispositivo implantado. É altamente recomendável que a equipe de implantação verifique se as Salas do Microsoft Teams estão fazendo logons no Pacote de Gerenciamento de Operações da Microsoft (se usado). Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade. Para saber mais, confira esta [lista de verificação de implantação útil.](console.md#microsoft-teams-rooms-deployment-checklist)

Recomendamos que, como parte da adoção geral do Teams ou do Skype for Business, configure arquivos de construção para o Painel de Qualidade de Chamada (CQD), monitore tendências de qualidade e participe do processo de Revisão de Qualidade da Experiência. Para obter mais informações, consulte [Melhorar e monitorar a qualidade da chamada para o Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você vai querer atualizar seu registro de ativos com o nome da sala, o nome do dispositivo Salas do Microsoft Teams, a conta de recurso de Salas do Microsoft Teams e dispositivos periféricos atribuídos (e quais portas USB eles usam). 

_Tabela de ativos de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Número de série do Microsoft Teams Rooms.**  | **Dispositivos periféricos/ Nós seriais./ Portas**  | **Nome do computador salas do Microsoft Teams**  | **Conta de serviço salas do Microsoft Teams**  | **Data implantada** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Curie         | Média        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


