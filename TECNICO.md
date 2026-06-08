# Lead CursoAds — Documento Técnico

## Visão Geral

Página de captura de leads para o curso de Ads em marketplaces. Versão paga (funil pago) com rastreamento de UTMs e integração n8n.

## Stack

| Camada | Tecnologia |
|--------|-----------|
| Frontend | HTML + CSS + JavaScript puro |
| Automação | n8n Webhook |
| Deploy | HostGator |

## Estrutura

```
lead-cursoads/
├── index.html
├── assets/
├── fonts/
├── hostgator_upload_pago/    # Arquivos prontos para upload
├── n8n-workflow-lead-cursoads.json   # Workflow n8n exportado
├── robots.txt
└── SEO-REPORT.md
```

## Workflow n8n

Arquivo `n8n-workflow-lead-cursoads.json` contém o workflow exportado. Importar diretamente no n8n para restaurar a automação de captação.

## Deploy

```bash
# Fazer upload do conteúdo de hostgator_upload_pago/ para a raiz do domínio via FTP
```
