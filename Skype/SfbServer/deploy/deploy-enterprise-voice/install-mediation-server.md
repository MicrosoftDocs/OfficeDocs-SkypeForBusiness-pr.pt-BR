---
title: Instalar os arquivos do Servidor de Mediação no Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumo: saiba como instalar os arquivos para o Servidor de Mediação no Skype for Business Server.'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830791"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Instalar os arquivos do Servidor de Mediação no Skype for Business Server
 
**Resumo:** Saiba como instalar os arquivos para o Servidor de Mediação no Skype for Business Server.
  
Para concluir com êxito este procedimento, você deve estar conectado no servidor no mínimo como um administrador local e um usuário de domínio com associação no grupo RTCUniversalReadOnlyAdmins.
  
Use as etapas neste tópico para executar o Assistente de Implantação do Skype for Business Server para instalar os arquivos do Servidor de Mediação em um computador que você adicionou a um pool de Servidor de Mediação depois de usar o Construtor de Topologias para definir e publicar o pool. Ao instalar arquivos do Servidor de Mediação, você também instala e atribui o certificado exigido por cada computador em um pool do Servidor de Mediação. 
  
> [!NOTE]
> Este tópico assume que você já definiu e publicou um pool de Servidor de Mediação autônomo em sua topologia, conforme descrito em Implantar um Servidor de Mediação no Construtor de Topologias no [Skype for Business Server.](deploy-a-mediation-server.md) 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar os arquivos em um pool do Servidor de Mediação autônomo

1. Na mídia de instalação, clique com o\Setup\amd64\Setup.exee clique _\<installation media\>_ **** em Executar **como Administrador.**
    
2. Na página **Local de instalação**, clique em **OK**.
    
3. Na página **Acordo de licença do usuário final**, clique em **Eu aceito** e em **OK**. (Obrigatório para continuar.)
    
4. Na página **Assistente de Implantação do Skype for Business Server,** clique em **Instalar ou Atualizar o Sistema do Skype for Business Server.**
    
5. Próximo a **Etapa 1: Instalar repositório de configuração local**, clique em **Executar** e siga as instruções na tela.
    
6. Na página **Configurar réplica local do repositório de gerenciamento central**, aceite o padrão **Recuperar diretamente no repositório de gerenciamento central** e clique em **Avançar**.
    
7. Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.
    
8. Próximo à **Etapa 2: Configurar ou Remover Componentes do Skype for Business Server,** clique em **Executar** e em **Próximo.**
    
9. Na página **Executar comandos**, quando o status da tarefa é exibido como **Concluído**, clique em **Finalizar**.
    
10. Próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar**. Siga as instruções na tela, aceitando as configurações padrões. O Servidor de mediação exige um certificado, você executará a **Etapa 3** duas vezes: uma vez para emitir um certificado necessário e novamente para atribui-lo.
    
11. Quando o certificado for emitido e atribuído corretamente, ao lado da **Etapa 4: Iniciar serviços**, clique em **Executar** e siga as instruções na tela.
    
12. Quando a **Etapa 4** for concluída com êxito, reinicie o servidor e faça o login no servidor como membro do grupo DomainAdmins.
    
13. No computador em que você está executando o Painel de Controle do Skype for Business Server, verifique na página **Topologia** do Painel de Controle do Skype for Business Server se o status do serviço do Servidor de Mediação é mostrado como uma marca de seleção verde. Se um X vermelho é exibido, selecione o Servidor de Mediação. No menu **Ações**, clique em **Iniciar todos os serviços**. 
    
Se você adicionou mais de um computador ao pool do Servidor de Mediação, execute as etapas deste procedimento em todos os outros computadores no pool do Servidor de Mediação. Se você não precisar instalar arquivos para o Servidor de Mediação para outros [computadores,](configure-trunks.md) siga os procedimentos em Configurar troncos no Skype for Business Server para definir as configurações para a conexão de tronco entre esse pool do Servidor de Mediação (ou todos os Servidores de Mediação em um site) e seu par.

