{
  "__inputs": [
    {
      "name": "DS_PROMETHEUS",
      "label": "Prometheus",
      "description": "Prometheus datasource for billpay metrics",
      "type": "datasource",
      "pluginId": "prometheus",
      "pluginName": "Prometheus"
    }
  ],
  "__requires": [
    { "type": "grafana", "id": "grafana", "name": "Grafana", "version": "9.0.0" },
    { "type": "datasource", "id": "prometheus", "name": "Prometheus", "version": "1.0.0" },
    { "type": "panel", "id": "timeseries", "name": "Time series", "version": "" },
    { "type": "panel", "id": "stat", "name": "Stat", "version": "" },
    { "type": "panel", "id": "piechart", "name": "Pie chart", "version": "" },
    { "type": "panel", "id": "table", "name": "Table", "version": "" },
    { "type": "panel", "id": "barchart", "name": "Bar chart", "version": "" }
  ],
  "annotations": {
    "list": [
      {
        "builtIn": 1,
        "datasource": { "type": "grafana", "uid": "-- Grafana --" },
        "enable": true,
        "hide": true,
        "iconColor": "rgba(0, 211, 255, 1)",
        "name": "Annotations & Alerts",
        "type": "dashboard"
      }
    ]
  },
  "description": "Monitors external_billpay_errors_total and downstream errors by error_code, exception_kind, and outcome",
  "editable": true,
  "fiscalYearStartMonth": 0,
  "graphTooltip": 1,
  "id": null,
  "links": [],
  "panels": [
    {
      "collapsed": false,
      "gridPos": { "h": 1, "w": 24, "x": 0, "y": 0 },
      "id": 100,
      "title": "📊 Summary",
      "type": "row"
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "thresholds" },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              { "color": "green", "value": null },
              { "color": "yellow", "value": 50 },
              { "color": "red", "value": 200 }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": { "h": 4, "w": 6, "x": 0, "y": 1 },
      "id": 1,
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "center",
        "orientation": "auto",
        "reduceOptions": { "calcs": ["lastNotNull"], "fields": "", "values": false },
        "textMode": "auto"
      },
      "title": "Total Errors (All Time)",
      "type": "stat",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum(external_billpay_errors_total{application=\"$application\"})",
          "legendFormat": "Total Errors",
          "refId": "A"
        }
      ]
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "thresholds" },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              { "color": "green", "value": null },
              { "color": "yellow", "value": 10 },
              { "color": "red", "value": 50 }
            ]
          },
          "unit": "reqps"
        },
        "overrides": []
      },
      "gridPos": { "h": 4, "w": 6, "x": 6, "y": 1 },
      "id": 2,
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "center",
        "orientation": "auto",
        "reduceOptions": { "calcs": ["lastNotNull"], "fields": "", "values": false },
        "textMode": "auto"
      },
      "title": "Error Rate (per sec)",
      "type": "stat",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum(rate(external_billpay_errors_total{application=\"$application\"}[$__rate_interval]))",
          "legendFormat": "Error Rate",
          "refId": "A"
        }
      ]
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "thresholds" },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              { "color": "green", "value": null },
              { "color": "yellow", "value": 5 },
              { "color": "red", "value": 20 }
            ]
          },
          "unit": "reqps"
        },
        "overrides": []
      },
      "gridPos": { "h": 4, "w": 6, "x": 12, "y": 1 },
      "id": 3,
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "center",
        "orientation": "auto",
        "reduceOptions": { "calcs": ["lastNotNull"], "fields": "", "values": false },
        "textMode": "auto"
      },
      "title": "Server Errors Rate (per sec)",
      "type": "stat",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum(rate(external_billpay_errors_total{application=\"$application\",outcome=\"server_error\"}[$__rate_interval]))",
          "legendFormat": "Server Error Rate",
          "refId": "A"
        }
      ]
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "thresholds" },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              { "color": "green", "value": null },
              { "color": "yellow", "value": 5 },
              { "color": "red", "value": 20 }
            ]
          },
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": { "h": 4, "w": 6, "x": 18, "y": 1 },
      "id": 4,
      "options": {
        "colorMode": "background",
        "graphMode": "area",
        "justifyMode": "center",
        "orientation": "auto",
        "reduceOptions": { "calcs": ["lastNotNull"], "fields": "", "values": false },
        "textMode": "auto"
      },
      "title": "Downstream Errors (All Time)",
      "type": "stat",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum(external_billpay_downstream_errors_total{application=\"$application\"})",
          "legendFormat": "Downstream Errors",
          "refId": "A"
        }
      ]
    },

    {
      "collapsed": false,
      "gridPos": { "h": 1, "w": 24, "x": 0, "y": 5 },
      "id": 101,
      "title": "📈 Error Rate Trends",
      "type": "row"
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "errors/sec",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 15,
            "gradientMode": "none",
            "hideFrom": { "legend": false, "tooltip": false, "viz": false },
            "lineInterpolation": "linear",
            "lineWidth": 2,
            "pointSize": 5,
            "scaleDistribution": { "type": "linear" },
            "showPoints": "auto",
            "spanNulls": false,
            "stacking": { "group": "A", "mode": "none" },
            "thresholdsStyle": { "mode": "off" }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [{ "color": "green", "value": null }]
          },
          "unit": "reqps"
        },
        "overrides": []
      },
      "gridPos": { "h": 9, "w": 12, "x": 0, "y": 6 },
      "id": 10,
      "options": {
        "legend": { "calcs": ["sum", "lastNotNull"], "displayMode": "table", "placement": "bottom", "showLegend": true },
        "tooltip": { "mode": "multi", "sort": "desc" }
      },
      "title": "Error Rate by error_code",
      "type": "timeseries",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (error_code) (rate(external_billpay_errors_total{application=\"$application\",exception_kind=~\"$exception_kind\",outcome=~\"$outcome\"}[$__rate_interval]))",
          "legendFormat": "{{error_code}}",
          "refId": "A"
        }
      ]
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "errors/sec",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 15,
            "gradientMode": "none",
            "hideFrom": { "legend": false, "tooltip": false, "viz": false },
            "lineInterpolation": "linear",
            "lineWidth": 2,
            "pointSize": 5,
            "scaleDistribution": { "type": "linear" },
            "showPoints": "auto",
            "spanNulls": false,
            "stacking": { "group": "A", "mode": "none" },
            "thresholdsStyle": { "mode": "off" }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [{ "color": "green", "value": null }]
          },
          "unit": "reqps"
        },
        "overrides": []
      },
      "gridPos": { "h": 9, "w": 12, "x": 12, "y": 6 },
      "id": 11,
      "options": {
        "legend": { "calcs": ["sum", "lastNotNull"], "displayMode": "table", "placement": "bottom", "showLegend": true },
        "tooltip": { "mode": "multi", "sort": "desc" }
      },
      "title": "Error Rate by exception_kind",
      "type": "timeseries",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (exception_kind) (rate(external_billpay_errors_total{application=\"$application\",error_code=~\"$error_code\",outcome=~\"$outcome\"}[$__rate_interval]))",
          "legendFormat": "{{exception_kind}}",
          "refId": "A"
        }
      ]
    },

    {
      "collapsed": false,
      "gridPos": { "h": 1, "w": 24, "x": 0, "y": 15 },
      "id": 102,
      "title": "🥧 Distribution Breakdowns",
      "type": "row"
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": { "hideFrom": { "legend": false, "tooltip": false, "viz": false } },
          "mappings": [],
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": { "h": 9, "w": 8, "x": 0, "y": 16 },
      "id": 20,
      "options": {
        "displayLabels": ["percent"],
        "legend": { "displayMode": "table", "placement": "bottom", "showLegend": true, "values": ["value", "percent"] },
        "pieType": "pie",
        "tooltip": { "mode": "single", "sort": "none" }
      },
      "title": "Error Distribution by error_code",
      "type": "piechart",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (error_code) (increase(external_billpay_errors_total{application=\"$application\",exception_kind=~\"$exception_kind\",outcome=~\"$outcome\"}[$__range]))",
          "legendFormat": "{{error_code}}",
          "refId": "A",
          "instant": true
        }
      ]
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": { "hideFrom": { "legend": false, "tooltip": false, "viz": false } },
          "mappings": [],
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": { "h": 9, "w": 8, "x": 8, "y": 16 },
      "id": 21,
      "options": {
        "displayLabels": ["percent"],
        "legend": { "displayMode": "table", "placement": "bottom", "showLegend": true, "values": ["value", "percent"] },
        "pieType": "donut",
        "tooltip": { "mode": "single", "sort": "none" }
      },
      "title": "Error Distribution by exception_kind",
      "type": "piechart",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (exception_kind) (increase(external_billpay_errors_total{application=\"$application\",error_code=~\"$error_code\",outcome=~\"$outcome\"}[$__range]))",
          "legendFormat": "{{exception_kind}}",
          "refId": "A",
          "instant": true
        }
      ]
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": { "hideFrom": { "legend": false, "tooltip": false, "viz": false } },
          "mappings": [],
          "unit": "short"
        },
        "overrides": []
      },
      "gridPos": { "h": 9, "w": 8, "x": 16, "y": 16 },
      "id": 22,
      "options": {
        "displayLabels": ["percent"],
        "legend": { "displayMode": "table", "placement": "bottom", "showLegend": true, "values": ["value", "percent"] },
        "pieType": "donut",
        "tooltip": { "mode": "single", "sort": "none" }
      },
      "title": "Error Distribution by outcome",
      "type": "piechart",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (outcome) (increase(external_billpay_errors_total{application=\"$application\",error_code=~\"$error_code\",exception_kind=~\"$exception_kind\"}[$__range]))",
          "legendFormat": "{{outcome}}",
          "refId": "A",
          "instant": true
        }
      ]
    },

    {
      "collapsed": false,
      "gridPos": { "h": 1, "w": 24, "x": 0, "y": 25 },
      "id": 103,
      "title": "📋 Stacked Trends & Heatmap",
      "type": "row"
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "errors/sec",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 60,
            "gradientMode": "none",
            "hideFrom": { "legend": false, "tooltip": false, "viz": false },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": { "type": "linear" },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": { "group": "A", "mode": "normal" },
            "thresholdsStyle": { "mode": "off" }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [{ "color": "green", "value": null }]
          },
          "unit": "reqps"
        },
        "overrides": []
      },
      "gridPos": { "h": 9, "w": 12, "x": 0, "y": 26 },
      "id": 30,
      "options": {
        "legend": { "calcs": ["sum"], "displayMode": "table", "placement": "right", "showLegend": true },
        "tooltip": { "mode": "multi", "sort": "desc" }
      },
      "title": "Stacked Error Rate — by error_code",
      "type": "timeseries",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (error_code) (rate(external_billpay_errors_total{application=\"$application\",outcome=~\"$outcome\",exception_kind=~\"$exception_kind\"}[$__rate_interval]))",
          "legendFormat": "{{error_code}}",
          "refId": "A"
        }
      ]
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "errors/sec",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 60,
            "gradientMode": "none",
            "hideFrom": { "legend": false, "tooltip": false, "viz": false },
            "lineInterpolation": "linear",
            "lineWidth": 1,
            "pointSize": 5,
            "scaleDistribution": { "type": "linear" },
            "showPoints": "never",
            "spanNulls": false,
            "stacking": { "group": "A", "mode": "normal" },
            "thresholdsStyle": { "mode": "off" }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [{ "color": "green", "value": null }]
          },
          "unit": "reqps"
        },
        "overrides": []
      },
      "gridPos": { "h": 9, "w": 12, "x": 12, "y": 26 },
      "id": 31,
      "options": {
        "legend": { "calcs": ["sum"], "displayMode": "table", "placement": "right", "showLegend": true },
        "tooltip": { "mode": "multi", "sort": "desc" }
      },
      "title": "Stacked Error Rate — by exception_kind",
      "type": "timeseries",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (exception_kind) (rate(external_billpay_errors_total{application=\"$application\",error_code=~\"$error_code\",outcome=~\"$outcome\"}[$__rate_interval]))",
          "legendFormat": "{{exception_kind}}",
          "refId": "A"
        }
      ]
    },

    {
      "collapsed": false,
      "gridPos": { "h": 1, "w": 24, "x": 0, "y": 35 },
      "id": 104,
      "title": "🗃️ Full Error Breakdown Table",
      "type": "row"
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "thresholds" },
          "custom": {
            "align": "auto",
            "cellOptions": { "type": "auto" },
            "inspect": false
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [
              { "color": "green", "value": null },
              { "color": "yellow", "value": 10 },
              { "color": "red", "value": 100 }
            ]
          }
        },
        "overrides": [
          {
            "matcher": { "id": "byName", "options": "error_code" },
            "properties": [{ "id": "custom.width", "value": 300 }]
          },
          {
            "matcher": { "id": "byName", "options": "exception_kind" },
            "properties": [{ "id": "custom.width", "value": 180 }]
          },
          {
            "matcher": { "id": "byName", "options": "outcome" },
            "properties": [{ "id": "custom.width", "value": 140 }]
          },
          {
            "matcher": { "id": "byName", "options": "Value" },
            "properties": [
              { "id": "displayName", "value": "Count" },
              { "id": "custom.width", "value": 120 },
              {
                "id": "custom.cellOptions",
                "value": { "type": "color-background", "mode": "gradient" }
              }
            ]
          }
        ]
      },
      "gridPos": { "h": 12, "w": 24, "x": 0, "y": 36 },
      "id": 40,
      "options": {
        "cellHeight": "sm",
        "footer": {
          "countRows": false,
          "enablePagination": false,
          "fields": "",
          "reducer": ["sum"],
          "show": true
        },
        "showHeader": true,
        "sortBy": [{ "desc": true, "displayName": "Count" }]
      },
      "title": "All Errors — error_code × exception_kind × outcome",
      "type": "table",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sort_desc(sum by (error_code, exception_kind, outcome) (increase(external_billpay_errors_total{application=\"$application\",error_code=~\"$error_code\",exception_kind=~\"$exception_kind\",outcome=~\"$outcome\"}[$__range])))",
          "legendFormat": "",
          "refId": "A",
          "instant": true,
          "format": "table"
        }
      ],
      "transformations": [
        { "id": "merge", "options": {} },
        {
          "id": "organize",
          "options": {
            "excludeByName": { "Time": true, "__name__": true, "application": true, "job": true, "instance": true },
            "renameByName": {
              "error_code": "Error Code",
              "exception_kind": "Exception Kind",
              "outcome": "Outcome",
              "Value": "Count"
            }
          }
        }
      ]
    },

    {
      "collapsed": false,
      "gridPos": { "h": 1, "w": 24, "x": 0, "y": 48 },
      "id": 105,
      "title": "🔻 Downstream Errors",
      "type": "row"
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "errors/sec",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 15,
            "gradientMode": "none",
            "hideFrom": { "legend": false, "tooltip": false, "viz": false },
            "lineInterpolation": "linear",
            "lineWidth": 2,
            "pointSize": 5,
            "scaleDistribution": { "type": "linear" },
            "showPoints": "auto",
            "spanNulls": false,
            "stacking": { "group": "A", "mode": "none" },
            "thresholdsStyle": { "mode": "off" }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [{ "color": "green", "value": null }]
          },
          "unit": "reqps"
        },
        "overrides": []
      },
      "gridPos": { "h": 8, "w": 12, "x": 0, "y": 49 },
      "id": 50,
      "options": {
        "legend": { "calcs": ["sum", "lastNotNull"], "displayMode": "table", "placement": "bottom", "showLegend": true },
        "tooltip": { "mode": "multi", "sort": "desc" }
      },
      "title": "Downstream Error Rate by service",
      "type": "timeseries",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (service) (rate(external_billpay_downstream_errors_total{application=\"$application\"}[$__rate_interval]))",
          "legendFormat": "{{service}}",
          "refId": "A"
        }
      ]
    },
    {
      "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
      "fieldConfig": {
        "defaults": {
          "color": { "mode": "palette-classic" },
          "custom": {
            "axisCenteredZero": false,
            "axisColorMode": "text",
            "axisLabel": "errors/sec",
            "axisPlacement": "auto",
            "barAlignment": 0,
            "drawStyle": "line",
            "fillOpacity": 15,
            "gradientMode": "none",
            "hideFrom": { "legend": false, "tooltip": false, "viz": false },
            "lineInterpolation": "linear",
            "lineWidth": 2,
            "pointSize": 5,
            "scaleDistribution": { "type": "linear" },
            "showPoints": "auto",
            "spanNulls": false,
            "stacking": { "group": "A", "mode": "none" },
            "thresholdsStyle": { "mode": "off" }
          },
          "mappings": [],
          "thresholds": {
            "mode": "absolute",
            "steps": [{ "color": "green", "value": null }]
          },
          "unit": "reqps"
        },
        "overrides": []
      },
      "gridPos": { "h": 8, "w": 12, "x": 12, "y": 49 },
      "id": 51,
      "options": {
        "legend": { "calcs": ["sum", "lastNotNull"], "displayMode": "table", "placement": "bottom", "showLegend": true },
        "tooltip": { "mode": "multi", "sort": "desc" }
      },
      "title": "Downstream Error Rate by status_class",
      "type": "timeseries",
      "targets": [
        {
          "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
          "expr": "sum by (status_class) (rate(external_billpay_downstream_errors_total{application=\"$application\"}[$__rate_interval]))",
          "legendFormat": "{{status_class}}",
          "refId": "A"
        }
      ]
    }
  ],
  "refresh": "30s",
  "schemaVersion": 38,
  "tags": ["billpay", "payments", "errors", "prometheus"],
  "templating": {
    "list": [
      {
        "current": {},
        "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
        "definition": "label_values(external_billpay_errors_total, application)",
        "hide": 0,
        "includeAll": false,
        "label": "Application",
        "multi": false,
        "name": "application",
        "options": [],
        "query": {
          "query": "label_values(external_billpay_errors_total, application)",
          "refId": "StandardVariableQuery"
        },
        "refresh": 2,
        "regex": "",
        "sort": 1,
        "type": "query"
      },
      {
        "current": {},
        "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
        "definition": "label_values(external_billpay_errors_total{application=\"$application\"}, error_code)",
        "hide": 0,
        "includeAll": true,
        "allValue": ".*",
        "label": "Error Code",
        "multi": true,
        "name": "error_code",
        "options": [],
        "query": {
          "query": "label_values(external_billpay_errors_total{application=\"$application\"}, error_code)",
          "refId": "StandardVariableQuery"
        },
        "refresh": 2,
        "regex": "",
        "sort": 1,
        "type": "query"
      },
      {
        "current": {},
        "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
        "definition": "label_values(external_billpay_errors_total{application=\"$application\"}, exception_kind)",
        "hide": 0,
        "includeAll": true,
        "allValue": ".*",
        "label": "Exception Kind",
        "multi": true,
        "name": "exception_kind",
        "options": [],
        "query": {
          "query": "label_values(external_billpay_errors_total{application=\"$application\"}, exception_kind)",
          "refId": "StandardVariableQuery"
        },
        "refresh": 2,
        "regex": "",
        "sort": 1,
        "type": "query"
      },
      {
        "current": {},
        "datasource": { "type": "prometheus", "uid": "${DS_PROMETHEUS}" },
        "definition": "label_values(external_billpay_errors_total{application=\"$application\"}, outcome)",
        "hide": 0,
        "includeAll": true,
        "allValue": ".*",
        "label": "Outcome",
        "multi": true,
        "name": "outcome",
        "options": [],
        "query": {
          "query": "label_values(external_billpay_errors_total{application=\"$application\"}, outcome)",
          "refId": "StandardVariableQuery"
        },
        "refresh": 2,
        "regex": "",
        "sort": 1,
        "type": "query"
      }
    ]
  },
  "time": { "from": "now-3h", "to": "now" },
  "timepicker": {},
  "timezone": "browser",
  "title": "External Billpay — Error Monitoring",
  "uid": "ext-billpay-errors-v1",
  "version": 1,
  "weekStart": ""
}
