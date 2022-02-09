---
title: Microsoft Teams atualização | Avaliação de Ambiente, Perguntas sobre Descoberta
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Use esta orientação para saber mais sobre os requisitos para avaliar corretamente seu ambiente atual para atualização para Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f947141a092d103f04adae07f0bdb60c8a2e0f66
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62418304"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>Questionário de descoberta - Avaliar seu ambiente

O seguinte conjunto de perguntas de lista de tabelas que ajudarão você a avaliar [seu ambiente antes de atualizar para Teams](upgrade-plan-journey-evaluate-environment.md):

- [Microsoft 365 ou Office 365 da organização](#microsoft-365-or-office-365-organization-details)
- [Resumo da plataforma de colaboração existente](#existing-collaboration-platform-summary)
- [Detalhes da implantação da plataforma de colaboração](#collaboration-platform-deployment-details)
- [Rede e acesso a serviços Microsoft 365 ou Office 365 serviços](#networking-and-access-to-microsoft-365-or-office-365-services)
- [Pontos de extremidade](#endpoints)
- [Operações](#operations)
- [Adoção e preparação](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 ou Office 365 da organização

É altamente recomendável que você tenha uma organização Microsoft 365 ou Office 365 enquanto trabalha com o questionário. Se você ainda não ativou ou configurou uma organização Microsoft 365 ou Office 365, consulte [Plan your setup of Microsoft 365 for business](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Use a tabela a seguir para capturar informações sobre a Microsoft 365 ou Office 365 organização.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Observe a organização de Microsoft 365 ou Office 365 de produção <br>nome e ID na coluna Resposta <br/>Se você tiver mais de um locatário <br>associado à sua organização, <br>observe todas as IDs. | Nome do locatário: <br/>ID do locatário:| |
> | Em quais regiões os locatários são implantados?| | |
> | Esses locatários Microsoft 365 ou Office 365 Multitenant ou <br>Dedicado? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> Dedicado | |
> | Quais produtos Microsoft Online estão em uso no momento? <br/>Observe o número de usuários habilitados para cada <br>na coluna Comentários. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> Outros| |
> | Qual nível de licença está habilitado para Skype para <br>Usuários do Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> Autônomo | O número de usuários <br>para cada SKU: |
> | Qual é a floresta atual do Active Directory <br>nível funcional no ambiente? <br/>Se houver mais de uma floresta, anote os detalhes <br>na coluna Comentários. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | O que você está usando para diretório <br>sincronização hoje? |<input type="checkbox"> Sem sincronização (somente nuvem) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Conexão <br/> <input type="checkbox"> Outro (Especificar no <br>&nbsp;&nbsp; &nbsp; Coluna Comentários.)| |
> | A identidade federada está implantada no momento? <br/>(Serviços de Federação do Active Directory ou <br>de terceiros) | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Se você estiver usando a identidade federada, qual é o <br>infraestrutura de federação? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> Federação de terceiros <br>&nbsp;&nbsp; &nbsp;gateway <br>&nbsp;&nbsp; &nbsp;(Observe os detalhes no <br>&nbsp;&nbsp; &nbsp; Coluna Comentários.) | |
> | Se você atualmente mantém uma Microsoft 365 ou Office 365 <br>tenant, é o domínio SMTP/SIP do seu <br>usuários direcionados associados ao locatário? | <input type="checkbox">N/A – Sem Microsoft 365 ou Office 365 <br>&nbsp;&nbsp; &nbsp;locatário in-locatária <br/> <input type="checkbox"> Não, SMTP/SIP dos usuários <br>&nbsp;&nbsp; &nbsp;domínio não está associado <br>&nbsp;&nbsp; &nbsp;com quaisquer locatários em <br>&nbsp;&nbsp; &nbsp;Microsoft 365 ou Office 365 <br/> <input type="checkbox"> Sim, SMTP/SIP dos usuários <br>&nbsp;&nbsp; &nbsp;domínio está associado <br>&nbsp;&nbsp; &nbsp;com um locatário existente <br>&nbsp;&nbsp; &nbsp;em Microsoft 365 ou Office 365 | |
> | Os UPNs do usuário combinam com o endereço SMTP principal? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não <br/> <input type="checkbox"> Inconsistentemente | |

## <a name="existing-collaboration-platform-summary"></a>Resumo da plataforma de colaboração existente

Use a tabela a seguir para capturar informações sobre a implantação da plataforma de colaboração existente.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | O Microsoft Teams está implantado? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | O Skype for Business está implantado? <br/>Para implantações locais e híbridas, certifique-se de <br>você observa a versão e a atualização cumulativa (CU) <br>detalhes na coluna Comentários. | <input type="checkbox">Sim, Microsoft 365 ou Office 365 <br/> <input type="checkbox">Sim, híbrido (com Microsoft 365 ou Office 365) <br/> <input type="checkbox"> Sim, local <br/> <input type="checkbox"> Sim, online, dedicado <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sim, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Sim, hospedado, compartilhado (terceiros) <br/> <input type="checkbox"> Não, outro | |
> | O Exchange está implantado? <br/>Para implantações locais e híbridas, certifique-se de <br>você observa a versão e os detalhes cu nos Comentários <br>column. | <input type="checkbox">Sim, Microsoft 365 ou Office 365 <br/> <input type="checkbox">Sim, híbrido (com Microsoft 365 ou Office 365) <br/> <input type="checkbox"> Sim, local <br/> <input type="checkbox"> Sim, online, dedicado <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sim, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Sim, hospedado, compartilhado <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Não, outro | |
> | O SharePoint está implantado? <br/>Para implantações locais e híbridas, certifique-se de <br>você observa a versão e os detalhes cu nos Comentários <br>column. | <input type="checkbox">Sim, Microsoft 365 ou Office 365 <br/> <input type="checkbox">Sim, híbrido (com Microsoft 365 ou Office 365) <br/> <input type="checkbox"> Sim, local <br/> <input type="checkbox"> Sim, online, dedicado <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sim, hospedado, dedicado <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Sim, hospedado, compartilhado <br>&nbsp;&nbsp; &nbsp;(terceiros) <br/> <input type="checkbox"> Não, outro | |
> | O Microsoft 365 ou Office 365 OneDrive for Business implantado? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Você tem outras plataformas de terceiros implantadas <br>e em uso hoje? Se sim, observe o número de usuários de <br>essas plataformas e os detalhes de uso nos Comentários <br>column. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> Outro (Especifique nos Comentários <br>&nbsp;&nbsp; &nbsp;column.) | Número de usuários: <br/>Detalhes:|
> | Você está planejando mover usuários desses terceiros <br>plataformas para Teams? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Qual é a solução atual de telefonia e conferência <br>dos usuários que estão no escopo dessa iniciativa? | | |
> | Você tem [SBCs que suportam o Roteamento](direct-routing-plan.md#supported-session-border-controllers-sbcs) Direto implantado para seus escritórios que estão no escopo dessa iniciativa? <br>Se Sim, anote os detalhes na coluna Comentários.| <input type="checkbox"> Sim <br/> <input type="checkbox"> Não ||

## <a name="collaboration-platform-deployment-details"></a>Detalhes da implantação da plataforma de colaboração

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se aplicável)

Se aplicável, capture os detalhes da sua implantação Teams usando a tabela de exemplo abaixo. Se você não tiver implantado Teams, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que tipos de usuários estão habilitados para o Microsoft Teams? | <input type="checkbox"> Todos os usuários na organização <br/> <input type="checkbox"> Usuários/grupos de usuários específicos <br>&nbsp;&nbsp; &nbsp;(Especifique na coluna Comentários) ||
> | Quais Teams recursos e modalidades estão em uso? | <input type="checkbox"> Conversas baseadas em canal <br/> <input type="checkbox"> Chat privado <br/> <input type="checkbox"> Acesso de convidados <br/> <input type="checkbox"> Reuniões de canal <br/> <input type="checkbox"> Reuniões privadas <br/> <input type="checkbox"> Chamada privada <br/> <input type="checkbox"> Reunião de canal ad hoc <br/> <input type="checkbox"> Vídeos em reuniões <br/> <input type="checkbox"> Compartilhamento de tela em reuniões <br/> <input type="checkbox"> Audioconferência <br/><input type="checkbox"> Aplicativos (aplicativos)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Guias<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bots <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conectores<br><input type="checkbox"> Integração personalizada de armazenamento em nuvem <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google Drive, Egnyte <br/> <input type="checkbox"> Integração de email de canal <br/> <input type="checkbox"> Outro (Especifique na coluna Comentários.) | |
> | Quais aplicativos você implantou para Teams? | | |
> | Você bloqueou especificamente alguma funcionalidade do Microsoft Teams? <br/>Se Sim, anote os detalhes na coluna Comentários. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não ||
> | Quais clientes Microsoft Teams estão em uso? | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows Mobile | |
> | Quem tem permissões para criar equipes? | <input type="checkbox"> Todos na organização <br>&nbsp;&nbsp; &nbsp;(Esta é a configuração padrão) <br/> <input type="checkbox"> Pessoas específicas <br>&nbsp;&nbsp; &nbsp;(Especifique na coluna Comentários.) | |
> | Você está usando os recursos de segurança e conformidade do Microsoft Teams? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (se aplicável)

Se aplicável, capture os detalhes da implantação Skype for Business Online usando a tabela de exemplo abaixo. Se você não tiver implantado a implantação Skype for Business Online, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Quais tipos de usuários estão habilitados para Skype <br>para o Business Online? | <input type="checkbox"> Todos os usuários na organização <br/> <input type="checkbox"> Usuários/grupos de usuários específicos <br>&nbsp;&nbsp; &nbsp;(Especifique na coluna Comentários) | |
> | Quais modalidades e recursos são atualmente <br>em uso hoje? | <input type="checkbox"> Mensagens Instantâneas e Presença (IM/P)<br/> <input type="checkbox"> Reuniões <br/> <input type="checkbox"> Federação <br/> <input type="checkbox"> Gravação de reunião <br/> <input type="checkbox"> Conferência de Áudio da Microsoft <br/> <input type="checkbox"> Audioconferência de terceiros <br>&nbsp;&nbsp; &nbsp;(Observe os detalhes na coluna Comentários.) <br/> <input type="checkbox"> Planos de Chamada (anteriormente chamada PSTN) <br/> <input type="checkbox"> Assistentes Automáticos Organizacionais <br/> <input type="checkbox"> Filas de chamada | |
> | Você bloqueou especificamente qualquer Skype para <br>Recursos do Business Online? <br>Se Sim, anote os detalhes na coluna Comentários. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Qual método você está usando ou planeja usar para <br>connect Sistema de Telefonia (anteriormente Cloud PBX) ao <br>O PSTN? <br/>Selecione todos os que se aplicam. | <input type="checkbox"> Planos de Chamada (anteriormente chamada PSTN) <br/> <input type="checkbox"> Conectividade PSTN local (aproveitando a conectividade existente <br>&nbsp;&nbsp; &nbsp;Skype for Business 2015 ou Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;deployment) <br/> <input type="checkbox"> Conectividade PSTN local (usando o Cloud Connector) | |
> | Você fez a portabilidade de algum número de telefone para a Microsoft? <br/>Isso é aplicável a Planos de Chamada e Áudio <br>Recursos de conferência. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business local (se aplicável)

Se aplicável, capture os detalhes da sua implantação Skype for Business usando a tabela de exemplo abaixo. Se você não tiver implantado Skype for Business local, ignore esta seção.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Quais versões do Lync ou Skype for Business atualmente <br>são implantados no local? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/> <input type="checkbox">Skype for Business Cloud Connector Edition | |
> | A implantação híbrida o Skype for Business Online está configurada? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Esse ambiente é hospedado e gerenciado por terceiros? <br/>Se Sim, anote os detalhes na coluna Comentários. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Quais modalidades e recursos estão em uso no momento <br>hoje? | <input type="checkbox"> Mensagens Instantâneas e Presença (IM/P) <br/> <input type="checkbox"> Reuniões <br/> <input type="checkbox"> Federação <br/> <input type="checkbox"> Gravação de reunião <br/> <input type="checkbox"> Chat Persistente / Chat de Grupo <br/> <input type="checkbox"> Conferência de Áudio da Microsoft <br>&nbsp;&nbsp; &nbsp;(anteriormente Discar em Conferência) em seu <br>&nbsp;&nbsp; &nbsp;Lync Server local ou <br>&nbsp;&nbsp; &nbsp;Skype for Business implantação <br/> <input type="checkbox"> Audioconferência de terceiros <br>&nbsp;&nbsp; &nbsp;(Observe os detalhes na coluna Comentários) <br/> <input type="checkbox">Enterprise Voice usando pSTN local <br>&nbsp;&nbsp; &nbsp;conectividade <br/> <input type="checkbox"> Planos de chamada (anteriormente chamada PSTN) via <br>&nbsp;&nbsp; &nbsp; Híbrido com Skype for Business Online | |
> | Quais versões do Servidor de Borda você tem implantadas? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 | |
> | Você tem o Lync ou o Skype for Business Edge implantados <br>em mais de um datacenter? <br/>Se Sim, anote os detalhes na coluna Comentários. | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Selecione serviços que sua função de Borda fornece hoje. | <input type="checkbox"> Acesso de usuário externo (usuários corporativos) <br/> <input type="checkbox"> Acesso de usuário remoto (externo anônimo <br>&nbsp;&nbsp; &nbsp;participantes da reunião) <br/> <input type="checkbox"> Federação <br/> <input type="checkbox"> Retransmissão de mídia | |
> | Qual dos seguintes recursos de chamada de voz você <br>atualmente tem dependências? <br/>Observe quaisquer dependências adicionais nos Comentários <br>column. | <input type="checkbox"> Opções de ocupado <br/> <input type="checkbox"> Estacionamento de chamada <br/> <input type="checkbox"> Retirada de chamada ou retirada de chamada de grupo <br/> <input type="checkbox"> Telefones de área comum ou "hot desking" <br/> <input type="checkbox"> Grupos de resposta ou grupos de busca <br/> <input type="checkbox"> Aparência de linha compartilhada <br/> <input type="checkbox"> Linha privada <br/> <input type="checkbox"> Caixa Postal <br/> <input type="checkbox"> Chamada via trabalho <br/> <input type="checkbox"> Números de emergência ou informações <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox"> Discagem de extensão <br/> <input type="checkbox"> Atendedor Automático <br/> <input type="checkbox"> Acesso ao assinante <br/> <input type="checkbox"> Dispositivos analógicos <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Mascaramento ou alteração da ID do chamador <br/> <input type="checkbox"> Roteamento baseado em local <br/> <input type="checkbox"> Roteamento de menor custo <br/> <input type="checkbox"> Telefones de elevador | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Rede e acesso a serviços Microsoft 365 ou Office 365 serviços

Use a tabela a seguir para capturar os detalhes de rede da sua organização e como seus usuários estão (ou serão) conectados aos serviços Microsoft 365 ou Office 365 da sua organização.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Como fazer (ou como) os usuários no escopo da migração <br>acessar Teams quando eles estão no escritório? <br/>Selecione todos os que se aplicam. | <input type="checkbox"> Conexão NAT roteada <br/> <input type="checkbox"> Servidor proxy <br/> <input type="checkbox"> Público Wi-Fi <br/> <input type="checkbox"> Recursos gerenciados (não públicos) Wi-Fi <br/> <input type="checkbox"> ExpressRoute (peering da Microsoft) ||
> | Se o acesso Microsoft 365 ou Office 365 for por meio de um servidor proxy, haverá <br>alguma maneira de ignorar o proxy? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | A Rota Expressa está sendo usada atualmente? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não <br/> <input type="checkbox"> Não, mas está sendo planejado | |
> | Você realizou uma Avaliação de Preparação de Rede? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Os usuários são obrigados a usar uma VPN ao se conectarem <br>recursos corporativos remotamente? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Se uma VPN for usada, Teams tráfego poderá ser excluído <br>a VPN para acessar Microsoft 365 ou Office 365 Serviços diretamente? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Sua rede dá suporte a QoS? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Você pode priorizar o Teams de áudio e vídeo <br>para impulsionar uma experiência de alta qualidade? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Todos os locais em uma região têm saída da Internet, <br>ou a saída da Internet é centralizada para toda a região? | <input type="checkbox"> Acesso regional à Internet <br/> <input type="checkbox"> Acesso centralizado à Internet | |

## <a name="endpoints"></a>Pontos de extremidade

Use a tabela a seguir para capturar os detalhes dos clientes e pontos de extremidade em uso.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Que sistema operacional de área de trabalho os usuários estão utilizando? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Especifique a versão na coluna Comentários.) <br/> <input type="checkbox"> Linux (Especifique a distribuição na coluna Comentários.) <br/> <input type="checkbox"> Outros (Observe os detalhes na coluna Comentários.) | |
> | Qual versão do Microsoft Office é implantada <br>para esses dispositivos? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office para Mac 2011 <br/> <input type="checkbox">Office para Mac 2016 <br/> <input type="checkbox"> Outros (Observe os detalhes na coluna Comentários.) | |
> | Qual Office tecnologia de implantação está em uso <br>em sua organização? | <input type="checkbox"> MSI <br/> <input type="checkbox"> Clique para executar | |
> | Quais são os dispositivos móveis permitidos e suportados <br>plataformas em uso? <br/>Selecione todos os que se aplicam. | <input type="checkbox">Windows <br/> <input type="checkbox"> Mobile <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Outros (Observe os detalhes na coluna Comentários.) | |
> | Como os dispositivos móveis são fornecidos? <br/>Selecione todos os que se aplicam. | <input type="checkbox"> Dispositivos corporativos <br/> <input type="checkbox"> Traga seu próprio dispositivo | |
> | Quais dispositivos os usuários atualmente usam para acessar <br>serviços de voz e conferência <br>(handsets, fones de ouvido, telefones, vídeo)? | | |

## <a name="operations"></a>Operações

Use a tabela a seguir para capturar os detalhes dos aspectos operacionais do seu ambiente.

> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Qual é o seu modelo de operações para o Lync Server, <br>Skype for Business Server, Microsoft 365 ou Office 365 implantação <br>hoje? | | |
> | Você pode delinear a disposição de suporte atual para <br>Lync Server, Skype for Business Server, Microsoft 365 ou Office 365? | | |
> | Se você estiver implantando em vários países ou regiões, <br>cada país/região tem sua própria IT/telefonia <br>equipe para trabalhar com ou isso será gerenciado centralmente? | <input type="checkbox"> Operações regionais e suporte <br/> <input type="checkbox"> Operações centralizadas e suporte | |
> | Você está seguindo a [Metodologia de Qualidade de Chamada](quality-of-experience-review-guide.md)? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não | |
> | Você atribuiu um indivíduo ou uma equipe ao <br>Função de Defensor da Qualidade para a plataforma de colaboração <br>em uso? | <input type="checkbox"> Sim <br/> <input type="checkbox"> Não ||
> | Como monitorar seu Lync Server, Skype para <br>Business Server, Microsoft 365 ou Office 365 implantação? | | |
> | Você tem problemas de qualidade das chamadas? | <input type="checkbox"> Sim<br/> <input type="checkbox"> Não | |
> | Como e quando você fornece treinamento para seu <br>helpdesk em novos serviços e recursos? | | |

## <a name="adoption-and-readiness"></a>Adoção e preparação

Use a tabela a seguir e registre o estado atual de adoção e preparação de sua organização.

>
> | Pergunta | Resposta | Comentários |
> |---|---|---|
> | Qual é o uso ativo atual de <br>Skype for Business? | **__** % total de usuários ativos versus usuários habilitados | |
> | Como sua organização está usando <br>Skype for Business? | Conversas privadas <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chamando <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartilhamento<br> Reuniões <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferência<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Compartilhamento<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chamando | |
> | Sua organização tem uma adoção de usuário <br>e Equipe de Gerenciamento de Alterações? | <input type="checkbox"> Sim<br/> <input type="checkbox"> Não | |
> | Como medir o sucesso da tecnologia no momento <br>lançamentos como Skype for Business? | | |
> | Qual porcentagem da sua base de usuários você diria que tem <br>adotado Skype for Business? | | |
> | Qual é a opinião dos usuários a respeito do Skype for Business? | <input type="checkbox"> Bom <br/> <input type="checkbox"> Neutro <br/> <input type="checkbox"> Bad | |
> | Qual das seguintes melhores descreve a adoção <br>estratégia usada para sua Skype for Business <br>implantação? | <input type="checkbox"> Amplo alcance: campanha de email com <br>&nbsp;&nbsp; &nbsp;links para treinamento <br/> <input type="checkbox"> Expandido: amplo alcance mais uma variedade <br>&nbsp;&nbsp; &nbsp;de campanhas de conscientização (cartazes, <br>&nbsp;&nbsp; &nbsp;eventos, campeões) e treinamento <br>&nbsp;&nbsp; &nbsp;(vídeos, guias de usuário, pessoalmente) <br/> <input type="checkbox"> Personalizado: expandido, mais direcionado <br>&nbsp;&nbsp; &nbsp;mensagens e treinamento por persona <br/> <input type="checkbox"> Outros <br>&nbsp;&nbsp; &nbsp;(Observe os detalhes na coluna Comentários.) | |


