---
title: Configurar os Skype for Business Server que serão monitorados
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Resumo: instale os arquivos de agente do Operations Manager no computador Skype for Business Server 2019 a ser monitorado e configure o computador para atuar como um proxy System Center de segurança.'
ms.openlocfilehash: 975c9eaa7d70720fefa52b8adc84b4f17200f972
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859638"
---
# <a name="configure-the-skype-for-business-server-computers-to-monitore"></a>Configurar os computadores Skype for Business Server para monitorar

**Resumo:** Instale os arquivos de agente do Operations Manager no computador Skype for Business Server 2019 a ser monitorado e configure o computador para atuar como um proxy System Center de segurança.

Cada Skype for Business Server 2019 que você deseja monitorar deve ser capaz de auto-relatar sua existência ao servidor de gerenciamento. Para habilitar esse processo, você deve instalar os arquivos de agente do Operations Manager em cada um dos computadores a serem monitorados. Depois de instalar os arquivos do agente, você deve configurar o computador para atuar como um proxy System Center usuário. Certifique-se de que você instalou e configurou os Skype for Business Server nesses computadores antes de realizar esses procedimentos.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Instalando um Certificado no Nó Inspetor Localizado Fora da Rede do Perímetro
<a name="watcher_node_outside"> </a>

System Center Agentes do Operations Manager em execução em uma rede de perímetro (como um servidor de borda do Skype for Business Server), fora da empresa (como um nó do watcher de transações sintéticas externo) ou em um limite de confiança do Active Directory, podem exigir a configuração de um servidor gateway do Gerenciador de Operações System Center. Essa função de servidor permite que os agentes que não têm uma relação de confiança com o Servidor de Gerenciamento Raiz levantem alertas. Para obter detalhes, consulte [Managing Gateway Servers in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12)).

Se você implantar um agente em um desses locais, também precisará solicitar e configurar um certificado que habilita o nó do watcher a enviar alertas para o System Center Operations Manager. Para simplificar esse processo, a equipe do Operations Manager criou um conjunto de utilitários que permitem que você solicite e instale o tipo certo de certificado no computador nó watcher. Para obter detalhes e baixar esses [utilitários, consulte Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://techcommunity.microsoft.com/t5/system-center-blog/obtaining-certificates-for-non-domain-joined-agents-made-easy/ba-p/340467).

### <a name="installing-the-operation-manager-agent-files"></a>Instalando os Arquivos de Agente do Gerenciador de Operações

1. Em sua System Center de configuração, clique duas vezes em **Setup.exe**.

2. No assistente de System Center de instalação do Operation Manager, clique em **Instalar o Agente do Gerenciador** de Operações , do Agente de Instalação em Instalações Opcionais

3. No assistente System Center de configuração, na página Bem-vindo ao assistente de Instalação do System Center Operations Manager, clique em **Próximo**.

4. Na página Pasta de Destino, selecione a pasta onde os arquivos do Agente do Gerenciador de Operações serão instalados e clique em **Próximo**.

5. Na página Configuração do Grupo de Gerenciamento, selecione **Especificar informações do Grupo de Gerenciamento** e clique em **Próximo**.

6. Na página Configuração do Grupo de Gerenciamento, digite  o nome do seu Grupo de Gerenciamento do Operations Manager na caixa Nome do Grupo de Gerenciamento e digite o nome de host do servidor do Operations Manager (por exemplo, atl-scom-001) na caixa **Servidor** de Gerenciamento. Se você alterou o número de porta usado pelo Operations Manager, insira o novo número de porta na caixa **Porta do Servidor de** Gerenciamento. Caso contrário, deixe a porta no valor padrão de 5723 e clique em **Próximo**.

7. Na página Conta de Ação do Agente, selecione **Sistema Local** e clique em **Próximo**.

8. Na página Do Microsoft Update, selecione **Não quero usar o Microsoft Update** e clique em **Próximo**.

9. Na página Pronto para Instalar, clique em **Instalar**.

10. Na página Concluindo o assistente de Instalação do System Center Operations Manager, clique em **Concluir**.

11. Clique em **Sair**.

Para System Center 2012, você pode verificar se o agente foi criado clicando em **Iniciar**, clicando em Todos os **Programas,** clicando no System Center Operations **Manager 2012** e clicando em **Operações 2012 Manager Shell**. Na Shell do Operations Manager, digite o seguinte comando Windows PowerShell e pressione ENTER:
```PowerShell
Get-SCOMAgent
```

Uma lista de todos os seus agentes do Operations Manager será exibida.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configurando o computador Skype for Business Server para participar da descoberta System Center descoberta
<a name="watcher_node_outside"> </a>

Para garantir que o novo agente Skype for Business Server participe do processo de descoberta do System Center Operations Manager, você deve concluir o seguinte procedimento em cada computador em que o console do System Center Operations Manager foi instalado:

1. Na guia Administração, clique em **Agente Gerenciado**.

2. Clique no **Assistente de Descoberta** e conclua o assistente para que o computador seja descoberto.

3. Reinicie o serviço de Agente de Saúde. Reiniciar o serviço forçará a descoberta do novo computador. Se você não reiniciar o serviço, poderá demorar até 4 horas antes que o novo computador seja descoberto pelo System Center Operations Manager.

4. Verifique se nenhum evento de erro foi registrado no log de eventos do Operations Manager.

5. O computador onde o agente é pressionado com êxito será mostrado na lista "Agente Gerenciado" e o computador onde o agente foi instalado manualmente será mostrado em "Gerenciamento Pendente", clique no nome do computador e aprove.

6. Clique com o botão direito no nome do computador e clique em **Propriedades**. Na caixa de diálogo Propriedades, na guia Segurança, selecione **Permitir que este agente haja como um proxy e descubra objetos gerenciados em outros computadores** e clique em **OK**.