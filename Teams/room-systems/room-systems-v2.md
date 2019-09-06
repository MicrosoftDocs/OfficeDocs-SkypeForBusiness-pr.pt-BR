---
title: Implantar salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber mais sobre como implantar salas do Microsoft Teams.
ms.openlocfilehash: 132c40c674824bb763ea2087318423ca3677f506
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775123"
---
# <a name="deployment-overview"></a>Visão geral de implantação

A implantação de salas do Microsoft Teams divide-se basicamente em fases:

- Confirmando que seus locais de implantação (salas) atendem às dependências de implantação
- Criando contas do Microsoft Teams ou do Skype for Business e do Exchange e atribuindo-as aos dispositivos de console (consulte [Configurar contas para salas do Microsoft Teams](room-systems-v2-configure-accounts.md))
- Recriação de imagens do Microsoft Surface tablets para funcionar como consoles de salas do Microsoft Teams (consulte [configurar um console de salas do Microsoft Teams](console.md) ou [implantar salas do Microsoft Teams guia de implantação em massa](room-systems-scale.md))
- Adicionais Configurando o pacote de gerenciamento de operações da Microsoft para seus sistemas (consulte [implantar gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md)
- Configurar consoles em salas de reunião e conectar os dispositivos periféricos de que você precisa (consulte a documentação do OEM para o conjunto de dispositivos)

Os técnicos do AV podem ser usados para a última tarefa, mas o departamento de ti da sua organização precisará fazer as outras partes do processo. 


## <a name="site-readiness"></a>Preparação do site 

Enquanto os dispositivos pedidos estão sendo entregues à sua organização, trabalhe com suas equipes e redes e em equipes de AV para garantir que as dependências de implantação sejam atendidas e que cada site e sala estejam prontos em termos de energia, rede e exibição. Além disso, certifique-se de que os requisitos de instalação física sejam atendidos. Para obter considerações sobre a instalação física, acesse o site do fabricante e aproveite a experiência da sua equipe de AV ao instalar e montar telas e executar o cabeamento.

Você pode saber mais sobre essas dependências nos links de diretrizes de planejamento abaixo:

-   [Verificar a disponibilidade da rede](srs-v2-prep.md#check-network-availability) 
-   [Certificados](srs-v2-prep.md#certificates)
-   [Proxy](srs-v2-prep.md#proxy)

**Dica de pro** -se você pretende usar servidores proxy para fornecer acesso ao Microsoft Teams ou ao Skype for Business Online, primeiro [Leia este artigo](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Observe que, quando se trata do tráfego do Skype for Business em servidores proxy, recomendamos ignorar os servidores proxy totalmente. O tráfego do Skype for Business já está criptografado, portanto, os servidores proxy não o tornam mais seguros. Como parte de sua implantação mais ampla, recomendamos que você siga as orientações em [avaliar meu ambiente](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) para planejar a largura de banda e avaliar a adequação da sua rede para o tráfego em tempo real.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos requisitos-chave para salas do Microsoft Teams.</li><li>Confirme que você forneceu largura de banda suficiente para cada site.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração do seu dispositivo.</li></ul>| 

## <a name="service-readiness"></a>Prontidão de serviço

Para se preparar para a implantação de salas do Microsoft Teams, siga estas teclas: tarefas centrais:

-   Defina os recursos da conta do serviço de salas do Microsoft Teams.
-   Prepare uma unidade organizacional e um grupo do Active Directory para manter suas contas do computador de salas e de serviço do Microsoft Teams e, opcionalmente, preparar objetos de política de grupo (GPOs) para habilitar a comunicação remota do PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Definir recursos da conta do serviço de salas do Microsoft Teams 

Dependendo dos cenários de colaboração que você decidiu habilitar com a implantação de salas do Microsoft Teams, será necessário determinar os recursos e as funcionalidades que atribui a cada conta de serviço de salas do Microsoft Teams que você habilitar.

| **Cenário** | **Descrição** | **Recurso da conta de serviço de salas do Microsoft Teams** |
|---------- |------------- | --- |
| Reuniões interativas            | Usando voz, vídeo e compartilhamento de tela; como deixar as salas do Microsoft Teams em um recurso que está em um livro                     | Habilitado para o Skype for Business, habilitado para Exchange (caixa de correio de recurso) |
| Conferência discada            | Habilitar reuniões iniciadas *diretamente* do console de salas do Microsoft Teams com coordenadas de conferência discada | Habilitado para conferência de áudio                                          |
| Chamadas PSTN de entrada/saída | Habilitar o console de salas do Microsoft Teams para fazer e receber chamadas PSTN                                         | Habilitado para o sistema telefônico                                                |

Para obter mais informações sobre contas de salas do Microsoft Teams, consulte [Configurar contas para salas do Microsoft Teams](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quais cenários você irá dar suporte e identifique os requisitos de licença para suas contas de serviço de salas do Microsoft Teams.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Prepare-se para o computador host e contas de serviço.</li></ul>| 


_Exemplo de tabela de planejamento de conta do serviço de salas do Microsoft Teams_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Recursos de sala futura**                                                 | **Recursos da conta de salas do Microsoft Teams**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| HQ de Londres | Curie         | Média        | 1 tela, áudio e vídeo, além de uma apresentação <br>Acesso à conferência discada<br> Acesso PSTN  | Habilitado para o Skype for Business, habilitado para Exchange (caixa de correio de recurso) <br>Habilitado para conferência de áudio <br>Habilitado para o sistema telefônico |
| HQ de Sydney | Pico          | Grande         | 2 telas, áudio e vídeo e apresentação<br>Acesso à conferência discada<br> Acesso PSTN  | Habilitado para o Skype for Business, habilitado para Exchange (caixa de correio de recurso)<br> Habilitado para conferência de áudio <br>Habilitado para o sistema telefônico |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Preparar-se para hospedar salas de equipe e contas de serviço do Microsoft Teams (opcional)

Para permitir que você gerencie e relate o seu computador de salas do Microsoft Teams e contas de serviço, prepare seu Active Directory local ou o Azure Active Directory (Azure AD). 

Defina um Active Directory local ou grupo do Azure AD para adicionar todas as contas do serviço de salas do Microsoft Teams (usuário) e, em seguida, criar relatórios de uso usando o cmdlet Get-CSUserSession do PowerShell em sua implantação de salas do Microsoft Teams. Por exemplo, crie um grupo chamado SkypeRoomSystemsv2-Service-Accounts. 


Defina uma unidade organizacional no Active Directory local ou na hierarquia do Azure AD para armazenar todas as contas do computador de salas do Microsoft Teams (se elas estiverem associadas ao domínio) e uma unidade organizacional para armazenar todas as contas de usuário das salas do Microsoft Teams. Se você criar uma unidade organizacional para as contas do computador de salas do Microsoft Teams, considere a possibilidade de desabilitar a herança para garantir que você aplique somente as políticas que pretende aplicar às salas do Microsoft Teams associadas a um domínio. 

Crie um objeto de política de grupo atribuído à unidade organizacional que contém as contas de computador das salas do Microsoft Teams. Use isso para: 

-   [Definir configurações de conta local e de energia](room-systems-v2-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Habilite o Windows Update.
-   Habilitar a comunicação remota do PowerShell. Você pode configurar um script de inicialização para executar um script simples: Enable-PSRemoting-Force

Você pode usar o PowerShell para executar várias atividades de gerenciamento remoto, incluindo obter e definir informações de configuração. A comunicação remota do PowerShell deve ser habilitada *antes que* qualquer gerenciamento remoto do PowerShell possa ocorrer e deve ser considerado como parte de seus processos de implantação ou configurado por meio da política de grupo. Para obter mais informações sobre esses recursos e ativá-los, consulte [manutenção e operações](room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuração e implantação 

O planejamento de configuração e implantação abrange as seguintes áreas-chave:

-   Provisionamento de conta
-   Instalação do software do dispositivo
-   Implantação de dispositivos
-   Aplicativo salas do Microsoft Teams e configuração de dispositivo periférico
-    Testes
-   Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta 

Cada dispositivo de salas do Microsoft Teams requer uma conta de recurso dedicada e exclusiva que deve ser habilitada para o Microsoft Teams ou o Skype for Business e o Exchange. Essa conta deve ter uma caixa de correio de sala hospedada no Exchange e estar habilitada como uma sala de reunião na implantação do teams ou do Skype for Business. No lado do Exchange, o processamento do calendário deve ser configurado para que o dispositivo possa aceitar automaticamente as solicitações de reunião recebidas. Para obter mais informações sobre como criar essas contas, consulte [Configurar contas para salas do Microsoft Teams](room-systems-v2-configure-accounts.md). 

**Dica de pro** – torne os nomes de exibição para essas contas descritivas e fáceis de entender. Estes são os nomes que os usuários verão ao procurar e adicionar sistemas de salas do Microsoft Teams a reuniões. Algumas organizações usam o*nome da sala*do *site*-da Convenção (*capacidade máxima da sala*)-RS, portanto, por exemplo Curie — uma sala de conferência de 12 pessoas em Londres — pode ter o nome de exibição Lon-Curie (12)-RS. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a Convenção de nomenclatura para suas contas de sala do Microsoft Teams.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do seu dispositivo.</li></ul>| 


### <a name="device-software-installation"></a>Instalação do software do dispositivo 

Ao planejar a implantação de salas do Microsoft Teams, você tem várias opções a serem consideradas para instalar o software necessário. Cenários e abordagens comuns estão descritos na tabela a seguir. 

| **Cenário**            | **Próximos**         |
|-------------------------|-----------------------|   
|Implantação de um pequeno número de dispositivos de salas do Microsoft Teams (<10). | Se estiver usando salas do Microsoft Teams com base em Surface pro, siga as [instruções de instalação para uma instalação por dispositivo](console.md). [Este vídeo prático orienta você pelo processo.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Se estiver usando uma solução integrada, implante usando a imagem do fornecedor e defina as configurações conforme necessário. |
| Implantando entre 10 e 50 dispositivos de um único fornecedor.     | Crie uma imagem baseada em WIM, pause após [a etapa 6 na orientação](console.md)e Capture uma imagem de distribuição para ser usada com a tecnologia de distribuição de clonagem.    |
| Implantar mais de 50 dispositivos de salas do Microsoft Teams, implantar dispositivos de mais de um fornecedor ou exigir agentes específicos da organização como parte da implantação. | Use uma plataforma de distribuição e desenvolvimento de software baseado em sequenciador de tarefas, como o [System Center Configuration Manager](room-systems-scale.md).  |

**Dica de pro** -cada sala do Microsoft Teams deve ter um nome de máquina válido e exclusivo na sua rede. Muitos sistemas de monitoramento e alerta exibem o nome do computador como um identificador de chave, portanto, é importante desenvolver uma Convenção de nomenclatura para implantações de salas do Microsoft Teams que permitem ao pessoal de suporte localizar facilmente as salas do Microsoft Teams que foram sinalizadas como requer uma ação. Um exemplo pode estar usando um padrão de MTR para o*nome da sala* do*site*-(MTR-Lon-Curie). 

Como parte da implantação, você também precisará considerar sua estratégia para gerenciar e configurar as [contas locais](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) que são criadas pelo instalador do aplicativo salas do Microsoft Teams.

Oferecemos orientação sobre como usar o monitor do [Microsoft Azure](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) para monitorar a implantação de salas do Microsoft Teams e o relato sobre a disponibilidade, erros de hardware/software e salas do Microsoft Teams, versão do aplicativo. Se você decidir usar o Microsoft Operations Management Suite, instale o agente do Operations Management Suite como parte do processo de instalação do software e configure as informações de conexão do espaço de trabalho para o seu espaço de trabalho. 

Uma consideração adicional é se as salas do Microsoft Teams serão Unidas ao domínio. Informações sobre os benefícios da junção de domínio podem ser encontradas no [domínio do sistema de salas do Skype](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Escolha a Convenção de nomenclatura do dispositivo de salas do Microsoft Teams a ser usada durante a implantação.</li><li>Decida se você ingressará em dispositivos de salas do Microsoft Teams no seu domínio e como gerenciar e configurar contas locais. </li><li>Decida se você usará o Operations Management Suite para monitorar a implantação de salas do Microsoft Teams.</li><li>Decida qual método você usará para implantar o software e os agentes no sistema de salas do Microsoft Teams em preparação para a implantação do dispositivo. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a abordagem de implantação do dispositivo.</li></ul>| 


### <a name="device-deployment"></a>Implantação de dispositivos

Depois de implantar o software nas unidades de salas do Microsoft Teams, crie seu plano para enviar os dispositivos e seus dispositivos periféricos atribuídos para suas salas e, em seguida, vá para a instalação e a configuração. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decidir quem vai gerenciar a implantação de site por site.</li><li> Identifique os recursos que instalarão os dispositivos de sala do Microsoft Teams no site e instale a configuração e o teste.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Iniciar o teste de dispositivo.</li></ul>| 

_Exemplo de tabela de implantação_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Sistema de salas do Microsoft Teams**  | **Dispositivos periféricos**  | **Salas do Microsoft Teams nome do computador**  | **Conta do recurso de salas do Microsoft Teams**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| HQ de Londres | Curie         | Média        |                                   |                  |                                          |                                             |
| HQ de Sydney | Pico          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Aplicativo salas do Microsoft Teams e configuração de dispositivo periférico 

Após a implantação física de cada sistema de salas do Microsoft Teams e dos dispositivos periféricos suportados conectados, você precisará configurar o aplicativo salas do Microsoft Teams para atribuir a conta de recursos de salas do Microsoft Teams e a senha criada anteriormente para habilitar o sistema de salas do Microsoft Teams para entrar no Microsoft Teams ou no Skype for Business e no Exchange. É fundamental aproveitar os periféricos de áudio e vídeo USB certificados vinculados em outro lugar do documento. Não fazer isso pode resultar em um comportamento imprevisível. 

Você pode configurar manualmente cada sistema de salas do Microsoft Teams. Você também pode usar um arquivo de configuração XML de sala de salas (Microsoft Teams) armazenado de forma centralizada para gerenciar as configurações do aplicativo e aproveitar um script de início de GPO para reaplicar a configuração desejada, sempre que o sistema de salas do Microsoft Teams for inicializado. 

Para obter mais informações sobre como usar o arquivo de configuração XML, consulte [gerenciar configurações de console de salas do Microsoft Teams remotamente com um arquivo de configuração XML](xml-config-file.md). 

Você pode usar o [PowerShell remoto](room-systems-v2-operations.md#remote-management-using-powershell) para extrair a configuração de salas do Microsoft Teams para reportar necessidades. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se você irá configurar manualmente cada sistema de salas do Microsoft Teams ou usar um arquivo XML central (um por dispositivo de salas do Microsoft Teams).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Defina sua abordagem de gerenciamento remoto.</li></ul>| 

### <a name="testing"></a> Testes

Após a implantação do sistema de salas do Microsoft Teams, você deve testá-lo. Verifique se os recursos listados na [ajuda das salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) estão trabalhando no dispositivo implantado. É altamente recomendável que a equipe de implantação Verifique se as salas do Microsoft Teams estão se conectando ao pacote de gerenciamento de operações da Microsoft (se usado). Também é importante fazer várias chamadas de teste e reuniões para verificar a qualidade. Para obter mais informações, consulte esta [lista de verificação de implantação útil](console.md#microsoft-teams-rooms-deployment-checklist).

Recomendamos que, como parte da distribuição geral do teams ou do Skype for Business, você configure a criação de arquivos para o painel de qualidade de chamada (CQD), monitore as tendências de qualidade e participe do processo de avaliação da qualidade da experiência. Para obter mais informações, consulte o [Guia de revisão da qualidade da experiência](https://aka.ms/qerguide). 

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você desejará atualizar o registro de ativos com o nome da sala, as salas do Microsoft Teams, o nome do dispositivo de salas conectado ao Microsoft Teams e os dispositivos periféricos atribuídos (e quais portas USB usam). 

_Tabela de ativos de exemplo_

| **Site**  | **Nome da sala** | **Tipo de sala** | **Salas do Microsoft Teams n º em série**  | **Dispositivos periféricos/em série nos./portas**  | **Salas do Microsoft Teams nome do computador**  | **Conta de serviço de salas do Microsoft Teams**  | **Data de implantação** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| HQ de Londres | Curie         | Média        |                                          |                                          |                                          |                                            |                   |
| HQ de Sydney | Pico          | Grande         |                                          |                                          |                                          |                                            |                   |


