{
  "name": "My workflow",
  "nodes": [
    {
      "parameters": {
        "sendTo": "={{ $json[\"option gmail\"] }}",
        "subject": "테스트]예비메일",
        "message": "예비 메일 입니다",
        "options": {
          "appendAttribution": false
        }
      },
      "type": "n8n-nodes-base.gmail",
      "typeVersion": 2.1,
      "position": [
        336,
        160
      ],
      "id": "d3b62ea3-3150-4f5a-97df-e9ec10427e0a",
      "name": "Send a message",
      "webhookId": "3f32f0fb-9b48-458c-94b3-7905de353973",
      "credentials": {
        "gmailOAuth2": {
          "id": "SbCrJImsncsNZkdL",
          "name": "Gmail account"
        }
      }
    },
    {
      "parameters": {
        "resource": "fileFolder",
        "filter": {
          "folderId": {
            "__rl": true,
            "value": "1Pv6b311XIgyYCViWIt8Rox6YguGzMHK2",
            "mode": "id"
          }
        },
        "options": {}
      },
      "type": "n8n-nodes-base.googleDrive",
      "typeVersion": 3,
      "position": [
        -672,
        16
      ],
      "id": "d6ed2e11-49e7-4da0-87da-096b5f1190c6",
      "name": "Search files and folders",
      "credentials": {
        "googleDriveOAuth2Api": {
          "id": "1GYKIVKdPPtdJvru",
          "name": "Google Drive account"
        }
      }
    },
    {
      "parameters": {
        "pollTimes": {
          "item": [
            {
              "mode": "everyMinute"
            }
          ]
        },
        "triggerOn": "specificFolder",
        "folderToWatch": {
          "__rl": true,
          "value": "https://drive.google.com/drive/folders/1Pv6b311XIgyYCViWIt8Rox6YguGzMHK2",
          "mode": "url"
        },
        "event": "fileCreated",
        "options": {}
      },
      "type": "n8n-nodes-base.googleDriveTrigger",
      "typeVersion": 1,
      "position": [
        -880,
        16
      ],
      "id": "ff6bdcd3-a236-4217-b668-1f5ac83a00dc",
      "name": "Google Drive Trigger",
      "credentials": {
        "googleDriveOAuth2Api": {
          "id": "1GYKIVKdPPtdJvru",
          "name": "Google Drive account"
        }
      }
    },
    {
      "parameters": {
        "options": {}
      },
      "type": "n8n-nodes-base.splitInBatches",
      "typeVersion": 3,
      "position": [
        -432,
        16
      ],
      "id": "76203293-d552-4a30-90ce-5ea423626966",
      "name": "Loop Over Items1"
    },
    {
      "parameters": {
        "operation": "download",
        "fileId": {
          "__rl": true,
          "value": "={{ $json.id }}",
          "mode": "id"
        },
        "options": {}
      },
      "type": "n8n-nodes-base.googleDrive",
      "typeVersion": 3,
      "position": [
        -240,
        160
      ],
      "id": "1ac04c69-fba0-4b3e-a45c-3ef58a37a412",
      "name": "Download file",
      "credentials": {
        "googleDriveOAuth2Api": {
          "id": "1GYKIVKdPPtdJvru",
          "name": "Google Drive account"
        }
      }
    },
    {
      "parameters": {
        "documentId": {
          "__rl": true,
          "value": "https://docs.google.com/spreadsheets/d/1fTqGWc9GXKq1UlGMHgnoDS-MMMtyGZQso04pjXeXhfc/edit?gid=0#gid=0",
          "mode": "url"
        },
        "sheetName": {
          "__rl": true,
          "value": "gid=0",
          "mode": "list",
          "cachedResultName": "시트1",
          "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1fTqGWc9GXKq1UlGMHgnoDS-MMMtyGZQso04pjXeXhfc/edit#gid=0"
        },
        "options": {}
      },
      "type": "n8n-nodes-base.googleSheets",
      "typeVersion": 4.7,
      "position": [
        160,
        160
      ],
      "id": "909c3dc3-6562-4892-ab5b-5965620ec215",
      "name": "Get row(s) in sheet",
      "credentials": {
        "googleSheetsOAuth2Api": {
          "id": "BdlVbC8A35ASVnVW",
          "name": "Google Sheets account"
        }
      }
    },
    {
      "parameters": {
        "operation": "text",
        "options": {}
      },
      "type": "n8n-nodes-base.extractFromFile",
      "typeVersion": 1,
      "position": [
        -48,
        160
      ],
      "id": "a05410a0-8b4e-4247-802c-0ef0d71d3ad5",
      "name": "Extract from File"
    }
  ],
  "pinData": {},
  "connections": {
    "Search files and folders": {
      "main": [
        [
          {
            "node": "Loop Over Items1",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Google Drive Trigger": {
      "main": [
        [
          {
            "node": "Search files and folders",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Loop Over Items1": {
      "main": [
        [],
        [
          {
            "node": "Download file",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Download file": {
      "main": [
        [
          {
            "node": "Extract from File",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Send a message": {
      "main": [
        [
          {
            "node": "Loop Over Items1",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Get row(s) in sheet": {
      "main": [
        [
          {
            "node": "Send a message",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Extract from File": {
      "main": [
        [
          {
            "node": "Get row(s) in sheet",
            "type": "main",
            "index": 0
          }
        ]
      ]
    }
  },
  "active": false,
  "settings": {
    "executionOrder": "v1"
  },
  "versionId": "19fbdb1e-8cde-4d7d-8eda-2faa6de77a1b",
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "5b8849734022ae03569d5466c1074e2a90b8c684ac36b447ec17db19159f08d8"
  },
  "id": "UDAbh23PnpN58gbg",
  "tags": []
}