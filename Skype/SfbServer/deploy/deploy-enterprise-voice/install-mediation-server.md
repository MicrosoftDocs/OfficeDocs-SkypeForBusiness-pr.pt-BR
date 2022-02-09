---
title: Instalar os arquivos para o Servidor de Mediação Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumo: saiba como instalar os arquivos para o Servidor de Mediação Skype for Business Server.'
ms.openlocfilehash: e74c966cc43b9768b107aff559429eb8a639e2cd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397444"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Instalar os arquivos para o Servidor de Mediação Skype for Business Server
 
**Resumo:** Saiba como instalar os arquivos para o Servidor de Mediação Skype for Business Server.
  
Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.
  
Use as etapas deste tópico para executar o Assistente de Implantação do Skype for Business Server para instalar os arquivos do Servidor de Mediação em um computador adicionado a um pool do Servidor de Mediação depois de usar o Construtor de Topologias para definir e publicar o pool. Ao instalar o Servidor de Mediação de Arquivos, você também instala e atribui o certificado exigido por cada computador em um pool do Servidor de Mediação. 
  
> [!NOTE]
> Este tópico pressupa que você já definiu e publicou um pool de Servidor de Mediação autônomo em sua topologia, conforme descrito em [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar os arquivos em um pool do Servidor de Mediação autônomo

1. Na mídia de instalação, clique com  _\<installation media\>_ o botão **direito do mouse\Setup\amd64\Setup.exe** e clique **em Executar como Administrador**.
    
2. Na página **Local de instalação**, clique em **OK**.
    
3. Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)
    
4. Na página **Skype for Business Server Assistente de Implantação**, clique **em Instalar ou Atualizar Skype for Business Server Sistema**.
    
5. Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.
    
6. Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.
    
7. Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.
    
8. Próximo à **Etapa 2: Configurar ou Remover Skype for Business Server Componentes**, clique em **Executar** e clique em **Próximo**.
    
9. Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.
    
10. Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribui-lo.
    
11. Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.
    
12. Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.
    
13. No computador em que você está executando Skype for Business Server Painel de Controle, verifique na página **Topologia** do Painel de Controle Skype for Business Server que o status do serviço do Servidor de Mediação é mostrado como uma marca de verificação verde. Se um X vermelho é exibido, selecione o Servidor de Mediação. No menu **Ações**, clique em **Iniciar todos os serviços**. 
    
Se você adicionou mais de um computador ao pool do Servidor de Mediação, execute as etapas deste procedimento em todos os outros computadores no pool do Servidor de Mediação. Se você não precisar instalar arquivos para o Servidor de Mediação para outros computadores, siga os procedimentos em [Configurar troncos no Skype for Business Server para definir configurações para a](configure-trunks.md) conexão de tronco entre esse pool do Servidor de Mediação (ou todos os Servidores de Mediação em um site) e seus pares.

